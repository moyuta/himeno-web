<template>
  <div>
    <swiper
      v-bind="swiperOptions"
      :modules="[Thumbs]"
      :thumbs="{ swiper: thumbsSwiper }"
      class="main-swiper"
    >
      <swiper-slide
        v-for="(slide, index) in slides"
        :key="index"
        class="slide-image"
      >
        <img :src="slide.src" :alt="slide.title" />
      </swiper-slide>
      <div class="swiper-button-next swiper-next" slot="button-next"></div>
      <div class="swiper-button-prev swiper-prev" slot="button-prev"></div>
    </swiper>
    <swiper
      v-bind="thumbnailsSwiperOptions"
      @swiper="setThumbsSwiper"
      :modules="[Thumbs]"
      watch-slides-progress
      class="thumbnails-swiper"
    >
      <swiper-slide
        v-for="(slide, index) in slides"
        :key="index"
        class="thumbnails-slide-image"
      >
        <img :src="slide.src" :alt="slide.title" />
      </swiper-slide>
    </swiper>
  </div>
</template>


<script>
import { ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import SwiperCore, { Thumbs, Navigation } from "swiper";
import "swiper/swiper-bundle.min.css";
SwiperCore.use([Thumbs, Navigation]);

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const swiper = ref(null);
    const thumbsSwiper = ref(null);
    const slides = ref([
      { src: "/_nuxt/assets/image/slide1.jpg", title: "Slide 1" },
      { src: "/_nuxt/assets/image/slide2.jpg", title: "Slide 2" },
      { src: "/_nuxt/assets/image/slide3.jpg", title: "Slide 3" },
      { src: "/_nuxt/assets/image/slide4.jpg", title: "Slide 4" },
      { src: "/_nuxt/assets/image/slide5.jpg", title: "Slide 5" },
    ]);
    const swiperOptions = ref({
      slidesPerView: 1,
      spaceBetween: 10,
      loop: true,
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
      },
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
      scrollbar: {
        el: ".swiper-scrollbar",
      },
      thumbs: {
        swiper: null,
      },
    });
    const thumbnailsSwiperOptions = ref({
      spaceBetween: 30,
      slidesPerView: 5,
      slideToClickedSlide: true,
      watchSlidesVisibility: true,
      watchSlidesProgress: true,
      loop: true,
      loopedSlides: 5,
    });

    // const onSwiper = (swiper) => {
    //   swiperOptions.value.thumbs.swiper = thumbnailsSwiper.value;
    //   swiper.value.thumbs.swiper = thumbnailsSwiper.value;
    // };

    // const onThumbnailsSwiper = (thumbnailsSwiper) => {
    //   thumbnailsSwiperOptions.value.thumbs.swiper = swiper.value;
    //   thumbnailsSwiper.value.thumbs.swiper = swiper.value;
    // };

    const setThumbsSwiper = (swiper) => {
      thumbsSwiper.value = swiper;
    };

    // onMounted(() => {
    //   swiperOptions.value.thumbs.swiper = thumbnailsSwiper.value;
    //   thumbnailsSwiperOptions.value.thumbs.swiper = swiper.value;
    // });

    return {
      swiper,
      thumbsSwiper,
      slides,
      swiperOptions,
      thumbnailsSwiperOptions,
      // onSwiper,
      // onThumbnailsSwiper,
      setThumbsSwiper,
      Thumbs,
    };
  },
};
</script>

<style lang='scss' scoped>
.slide-image {
  position: relative;
  padding-top: 60%;

  img {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
.thumbnails-swiper {
  margin-top: 10px;
  width: 80%;
}
.thumbnails-slide-image {
  position: relative;
  padding-top: 11%;
}
.thumbnails-slide-image img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.swiper-next,
.swiper-prev {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 40px;
  height: 40px;
  background-color: rgba(255, 255, 255, 0.5);
  z-index: 10;
  cursor: pointer;
}

/* 白の矢印 */
.swiper-next::after,
.swiper-prev::after {
  content: "";
  position: absolute;
  top: 50%;
  right: 0;
  width: 15px;
  height: 15px;
  border-top: 3px solid #fff;
  border-right: 3px solid #fff;
}
.swiper-next::after {
  right: 20px;
  transform: rotate(45deg) translateY(-50%);
}
.swiper-prev::after {
  top: 21%;
  left: 20px;
  transform: rotate(-135deg) translateY(-50%);
}
</style>

