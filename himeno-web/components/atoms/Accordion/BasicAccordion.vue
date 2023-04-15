<template>
  <div class="faq__list">
    
    <button class="faq__toggle" @click="onClick">
        <p>{{ text }}</p>
        <div>
        <p v-if="!isAccordion">+</p>
        <p v-else>-</p>
        </div>
    </button>
    
    
    <div class="faq__content" v-show="isAccordion">
      <p>
        {{ description }}
      </p>
    </div>

  </div>
</template>

<script>
export default {
  props: {
    text: { type: String, default: "製作時のエピソード（アコーディオン）" },
    description: {type: String, default: " アコーディオン展開イメージ昨今、情報技術は目まぐるしい勢いで進化を続け、インターネットでは、1日に膨大な量の情報が飛び交っています。インターネットで現代人が1日に触れる情報量は江戸時代の1年分とも言われています。"}
  },
  setup(){
    const isAccordion = ref(false)
    const onClick = () => {
        if(isAccordion) {
            isAccordion = false
        }else {
            isAccordion = true
        }
    }
    return {isAccordion}
  }
};
</script>

<style lang="scss" scoped>
  .faq__list {
    background: #666666;
    color: #fff;
    font-size: 53px;
  }

  .faq__title {
    position: relative;
    font-size: 53px;
  }

  .faq__content {
    font-size: 27px;
    background: #CCCCCC;
    
  }


</style>
