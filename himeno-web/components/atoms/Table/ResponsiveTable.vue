<template>
  <div>
    <table class="table">
      <thead>
        <tr>
          <th class="table__title" v-for="(title, key) in titles" :key="key">
            {{ title }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(table, key) in tables" :key="key">
          <td class="table__text">{{ table.text }}</td>
          <td class="table__img">
            <img :src="table.src" :alt="table.alt" />
          </td>
          <td class="table__point">{{ table.point }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    color: { type: String, default: "#fff" },
    background: { type: String, default: "#999999" },
  },

  setup() {
    const titles = reactive(["空間に与える印象", "写真", "使用のポイント"]);
    const tables = reactive([
      {
        text: "空間を和らげ、安らぎを感じる",
        src: "/_nuxt/assets/image/table-img.jpg",
        alt: "イメージ画像",
        point:
          "昨今、情報技術は目まぐるしい勢いで進化を続け、インターネットでは、1日に膨大な量の情報が飛び交っています。インターネットで現代人が1日に触れる情報量は江戸時代の1年分とも言われています。",
      },
      {
        text: "空間を和らげ、安らぎを感じる",
        src: "/_nuxt/assets/image/table-img.jpg",
        alt: "イメージ画像",
        point:
          "昨今、情報技術は目まぐるしい勢いで進化を続け、インターネットでは、1日に膨大な量の情報が飛び交っています。インターネットで現代人が1日に触れる情報量は江戸時代の1年分とも言われています。",
      },
      {
        text: "空間を和らげ、安らぎを感じる",
        src: "/_nuxt/assets/image/table-img.jpg",
        alt: "イメージ画像",
        point:
          "昨今、情報技術は目まぐるしい勢いで進化を続け、インターネットでは、1日に膨大な量の情報が飛び交っています。インターネットで現代人が1日に触れる情報量は江戸時代の1年分とも言われています。",
      },
      {
        text: "空間を和らげ、安らぎを感じる",
        src: "/_nuxt/assets/image/table-img.jpg",
        alt: "イメージ画像",
        point:
          "昨今、情報技術は目まぐるしい勢いで進化を続け、インターネットでは、1日に膨大な量の情報が飛び交っています。インターネットで現代人が1日に触れる情報量は江戸時代の1年分とも言われています。",
      },
    ]);
    return { titles, tables };
  },
};
</script>

<style lang="scss" scoped>
.table {
  font-size: rem(28);
  border-collapse: collapse;

  td,
  th {
    border: rem(1) solid #000;
    padding: rem(8);
    @include mq("sp") {
      padding: rem(20);
    }
  }

  tr {
    @include mq("sp") {
      display: grid;
    }
  }

  &__title {
    background: v-bind(background);
    padding: rem(40) 0;
    color: v-bind(color);
    @include mq("sp") {
      display: none;
    }
  }

  &__text {
    padding: 0 rem(20);
    width: 40%;
    @include mq("sp") {
      background: v-bind(background);
      color: v-bind(color);
      width: 100%;
      text-align: center;
      padding: rem(40) 0;
    }
  }

  &__img {
    width: 20%;
    @include mq("sp") {
      width: 100%;
    }
  }

  &__point {
    width: 40%;
    @include mq("sp") {
      width: 100%;
    }
  }
}
</style>
