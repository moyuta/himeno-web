<template>
  <div>
    <p>TOPページ</p>
    <LinkButton />
    <LinkButton
      text="お問合せ・お見積り"
      fontSize="50px"
      width="700px"
      height="140px"
      borderRadius="35px"
    />
    <CarouselSlider />
    <BasicTable />
  </div>
</template>

<script>
import { LinkButton } from "../components/atoms/Button";
import { CarouselSlider } from "../components/atoms/Carousel";
import { BasicTable } from "../components/atoms/Table";
export default {
  components: {
    LinkButton,
    CarouselSlider,
    BasicTable,
  },
  setup() {
    return {};
  },
};
</script>

<style></style>