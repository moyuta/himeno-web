<template>
  <div>
    <table class="table">
      <tbody>
        <tr v-for="(table, key) in tables" :key="key">
          <td class="table__name">{{ table.name }}</td>
          <td class="table__text">{{ table.text }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  setup() {
    const tables = reactive([
      { name: "竣工年：", text: "2017年" },
      { name: "計画地：", text: "愛知県名古屋市" },
      { name: "構造・面積：", text: "木造2階建　96㎡" },
      { name: "工期：", text: "2017年9月〜11月" },
      {
        name: "業務内容：",
        text: "インテリアデザイン、施工マネジメントイOXOXOXOXOXOOX",
      },
      { name: "クライアント：", text: "個人" },
    ]);
    return { tables };
  },
};
</script>
<style lang="scss" scoped>
.table {
  font-size: rem(28);
  border-collapse: collapse;

  td {
    border: 1px solid #000;
    padding: 8px;
  }

  &__name {
    background: #d8d8d8;
    padding: 0 rem(20);
  }
}
</style>