<template>
  <div>
    <AppHeader />
    <NuxtPage />
    <p>footer</p>
  </div>
</template>
<script>
import AppHeader from "../components/organisms/AppHeader";
export default {
  components: {
    AppHeader,
  },
  setup() {
    return {};
  },
};
</script>
