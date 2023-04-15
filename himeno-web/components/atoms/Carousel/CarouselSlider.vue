<template>
  <div>
    <swiper v-bind="swiperOptions" @swiper="onSwiper" class="main-swiper">
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
      @swiper="onThumbnailsSwiper"
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
import { Swiper, SwiperSlide } from "swiper/vue";
import SwiperCore, { Thumbs,Navigation, } from "swiper";
import "swiper/swiper-bundle.min.css";

SwiperCore.use([Thumbs, Navigation,]);

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiper: null,
      thumbnailsSwiper: null,
      swiperOptions: {
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
      },
      thumbnailsSwiperOptions: {
        spaceBetween: 30,
        slidesPerView: 5,
        centeredSlides: false,
        slideToClickedSlide: true,
        watchSlidesVisibility: true,
        watchSlidesProgress: true,
        loop: true,
        loopedSlides: 5,
      },
      slides: [
        { src: "/_nuxt/assets/image/slide1.jpg", title: "Slide 1" },
        { src: "/_nuxt/assets/image/slide2.jpg", title: "Slide 2" },
        { src: "/_nuxt/assets/image/slide3.jpg", title: "Slide 3" },
        { src: "/_nuxt/assets/image/slide4.jpg", title: "Slide 4" },
        { src: "/_nuxt/assets/image/slide5.jpg", title: "Slide 5" },
      ],
    };
  },
  methods: {
    onSwiper(swiper) {
      this.swiper = swiper;
      this.swiperOptions.thumbs.swiper = this.thumbnailsSwiper;
    },
    onThumbnailsSwiper(thumbnailsSwiper) {
      this.thumbnailsSwiper = thumbnailsSwiper;
      this.swiperOptions.thumbs.swiper = thumbnailsSwiper;
    },
  },
};
</script>

<style scoped>
.slide-image {
  position: relative;
  padding-top: 60%;
}
.slide-image img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  object-fit: cover;
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
  left: 20px;
  top: 21%;
  transform: rotate(-135deg) translateY(-50%);
}
</style>

