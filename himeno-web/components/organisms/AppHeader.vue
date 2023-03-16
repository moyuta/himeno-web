<template>
  <header class="header">
    <nav class="header__nav">
      <ul class="header__list">
        <!-- keyはfor文を何回目をとれる -->
        <!-- :keyは右辺が変数に変わっている -->
        <!-- v-for使用する場合はkeyは絶対つける -->
        <li class="header__item" v-for="(list, key) in lists" :key="key">
          <NuxtLink :to="list.path">{{ list.name }}</NuxtLink>
        </li>
      </ul>
    </nav>

    <!-- SP用 -->
    <div class="drawer">
      <input id="drawer__cb" type="checkbox" value="off" />
      <label id="drawer__icon" for="drawer__cb">
        <span></span>
        <span></span>
        <span></span>
      </label>
      <nav id="drawer__nav">
        <div class="drawer__container">
          <ul class="drawer__list">
            <li class="drawer__item" v-for="(list, key) in lists" :key="key">
              <NuxtLink :to="list.path">{{ list.name }}</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/">個人情報保護法について</NuxtLink>
            </li>
          </ul>
          <div class="drawer__icons">
            <a href="" class="drawer__icon">
              <img src="~/assets/image/icon-facebook.svg" alt="Facebook" />
            </a>
            <a href="" class="drawer__icon">
              <img src="~/assets/image/icon-instgram.svg" alt="instagram" />
            </a>
            <a href="" class="drawer__icon">
              <img src="~/assets/image/icon-pinterest.svg" alt="Pinterest" />
            </a>
          </div>
        </div>
      </nav>
    </div>
    <!-- <button @click="onClick('hoge')"></button> -->
  </header>
</template>
<script>
//コンポジションapi
//reactiveを使用する場合は配列もしくはオブジェクト
//オブジェクト=keyと値がセットになった者
//ref イント型（数字）テキスト型
//{path: "/contact" , text: "お問い合わせ"}
export default {
  setup() {
    const lists = reactive([
      { path: "/about", name: "ホーム" },
      { path: "/reason", name: "選ばれる理由" },
      { path: "/work", name: "ワークフロー" },
      { path: "/faq", name: "FAQ" },
      { path: "/example", name: "事例紹介" },
      { path: "/company", name: "会社概要" },
      { path: "/contact", name: "お問合せ・お見積" },
    ]);
    // const onClick = (text) => {
    //   console.log(text);
    // };
    return { lists };
  },
};
</script>
<style lang='scss' scoped>
.header__list {
  display: flex;
  gap: 30px;
}

.drawer {
  display: none;
}

.header__nav {
  @include mq("sp") {
    display: none;
  }
}

.drawer {
  @include mq("sp") {
    display: block;
  }
}

#drawer__nav {
  @include mq("sp") {
    background-color: #fff;
    box-sizing: border-box;
    height: 100%;
    padding: 75px 20px;
    position: fixed;
    right: -100%;
    top: 0;
    transition: transform 0.3s linear 0s;
    width: 100%;
    z-index: 1000;
  }
}

#drawer__icon {
  @include mq("sp") {
    background-color: #fff;
    cursor: pointer;
    display: block;
    height: 36px;
    position: fixed;
    right: 20px;
    text-align: center;
    top: 19.5px;
    width: 36px;
    transition: all 0.3s linear 0s;
    z-index: 1001;
  }
}

#drawer__icon span {
  @include mq("sp") {
    position: absolute;
    display: inline-block;
    width: 30px;
    height: 4px;
    background: #666666;
    right: 3px;
    transition: 0.1s ease-out;
  }
}
#drawer__icon span:nth-child(1) {
  @include mq("sp") {
    top: 6px;
  }
}
#drawer__icon span:nth-child(2) {
  @include mq("sp") {
    top: 50%;
    transform: translateY(-50%);
  }
}
#drawer__icon span:nth-child(3) {
  @include mq("sp") {
    bottom: 6px;
  }
}

#drawer__cb {
  @include mq("sp") {
    display: none;
  }
}

#drawer__cb:checked ~ #drawer__nav {
  @include mq("sp") {
    transform: translate(-100%);
  }
}

#drawer__cb:checked ~ #drawer__icon span:nth-child(1) {
  @include mq("sp") {
    top: 20px;
    transform: rotate(-45deg);
  }
}
#drawer__cb:checked ~ #drawer__icon span:nth-child(2) {
  @include mq("sp") {
    display: none;
  }
}
#drawer__cb:checked ~ #drawer__icon span:nth-child(3) {
  @include mq("sp") {
    bottom: 12px;
    transform: rotate(45deg);
  }
}

.drawer__container {
  @include mq("sp") {
    border: 1px solid #333;
    padding: 29.5px 50px 61.5px 38px;
    max-width: 334px;
    margin: auto;
    box-sizing: border-box;
  }
}

.drawer__item a {
  @include mq("sp") {
    color: #333;
    font-size: 22px;
  }
}
.drawer__icons {
  @include mq("sp") {
    display: flex;
    margin-top: 53px;
    gap: 8%;
  }
}
.drawer__icon {
  @include mq("sp") {
    width: 70px;
    flex-shrink: 0;
  }
}
</style>
