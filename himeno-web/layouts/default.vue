<template>
  <div>
    <AppHeader />
    <NuxtPage />
    <AppFooter />
    <LinkButton />
    <LinkButton
      text="お問合せ・お見積り"
      fontSize="50px"
      width="700px"
      height="140px"
      borderRadius="35px"
    />
    <CarouselSlider />
  </div>
</template>
<script>
import AppHeader from "../components/organisms/AppHeader";
import AppFooter from "../components/organisms/AppFooter";
import { LinkButton } from "../components/atoms/Button";
import { CarouselSlider } from "../components/atoms/Carousel";
export default {
  components: {
    AppHeader,
    AppFooter,
    LinkButton,
    CarouselSlider,
  },
  setup() {
    return {};
  },
};
</script>
