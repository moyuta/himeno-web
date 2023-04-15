<template>
  <NuxtLink :to="to" class="btn__link">{{ text }}</NuxtLink>
</template>

<script>
export default {
  props: {
    text: { type: String, default: "詳しく見る" },
    to: { type: String, default: "#" },
    color: { type: String, default: "#40407F" },
    width: { type: String, default: "330px" },
    height: { type: String, default: "84px" },
    fontSize: { type: String, default: "32px" },
    borderRadius: { type: String, default: "16px" },
  },
};
</script>
<style lang="scss" scoped>
.btn__link {
  background: v-bind(color);
  color: white;
  font-size: v-bind(fontSize);
  border-radius: v-bind(borderRadius);
  width: v-bind(width);
  height: v-bind(height);
  display: flex;
  justify-content: center;
  align-items: center;
  &:hover {
    opacity: 0.7;
  }
}

.font-size {
  font-size: rem(10);
}

</style>