<template>
  <footer class="footer">
    <div class="footer__inner">
      <div class="footer__top">
        <div class="footer__column">
          <figure class="footer__img">
            <img
              src="~/assets/image/footer-logo.svg"
              alt="CYPHER interior design & Construction"
            />
          </figure>
        </div>
        <div class="footer__column">
          <div class="footer__lists">
            <ul class="footer__list">
              <li class="footer__item" v-for="(list, key) in lists1" :key="key">
                <NuxtLink :to="list.path">{{ list.name }}</NuxtLink>
              </li>
            </ul>
            <ul class="footer__list">
              <li class="footer__item" v-for="(list, key) in lists2" :key="key">
                <NuxtLink :to="list.path">{{ list.name }}</NuxtLink>
              </li>
            </ul>
          </div>
        </div>
        <div class="footer__column">
          <div class="footer__wrap">
            <div class="footer__box">
              <p class="footer__text">株式会社ウラシコCYPHER （サイファー）</p>
            </div>
          </div>
          <div class="footer__icons">
            <a href="" class="footer__icon">
              <img src="~/assets/image/icon-facebook.svg" alt="Facebook" />
            </a>
            <a href="" class="footer__icon">
              <img src="~/assets/image/icon-instgram.svg" alt="instagram" />
            </a>
            <a href="" class="footer__icon">
              <img src="~/assets/image/icon-pinterest.svg" alt="Pinterest" />
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="footer__bottom">
      <p class="footer__copyright">
        Copyright(c) 店舗設計・デザイン・施工 CYPHER. AllRights Reserved
      </p>
    </div>
  </footer>
</template>
<script>
export default {
  setup() {
    const lists1 = reactive([
      { path: "/", name: "ホーム" },
      { path: "/about", name: "私たちについて" },
      { path: "/reason", name: "選ばれる理由" },
      { path: "/work", name: "ワークフロー" },
      { path: "/faq", name: "FAQ" },
      { path: "/example", name: "事例紹介" },
    ]);
    const lists2 = reactive([
      { path: "/company", name: "会社概要" },
      { path: "/contact", name: "お問合せ・お見積" },
      { path: "/privacy", name: "個人情報保護法について" },
    ]);
    return { lists1, lists2 };
  },
};
</script>
<style lang='scss' scoped>
.footer__inner {
  background: $brown;
  padding: rem(107) rem(120) rem(46);
  @include mq("sp") {
    padding: rem(30) rem(20);
  }
}

.footer__top {
  max-width: rem(1680);
  margin: auto;
  display: flex;
  @include mq("sp") {
    display: block;
  }
}

.footer__column:nth-child(2) {
  margin-left: rem(166);
  @include mq("sp") {
    margin-left: 0;
  }
}
.footer__column:nth-child(3) {
  margin-left: rem(122);
  @include mq("sp") {
    margin-left: 0;
  }
}

.footer__img {
  width: rem(300);
  @include mq("sp") {
    width: 60%;
    margin: auto;
  }
}

.footer__lists {
  display: flex;
  color: $white;
  @include mq("sp") {
    display: block;
    width: 70%;
    margin: rem(80) auto 0;
  }
}

.footer__list + .footer__list {
  margin-left: rem(118);
  @include mq("sp") {
    margin-left: 0;
    margin-top: rem(10);
  }
}

.footer__item {
  font-size: rem(22);
  white-space: nowrap;
}

.footer__item + .footer__item {
  margin-top: rem(10);
}

.footer__wrap {
  border: solid rem(2) $white;
  padding: rem(10);
  @include mq("sp") {
    border: none;
  }
}

.footer__box {
  width: rem(580);
  border: solid rem(2) $white;
  padding: rem(177) rem(20) rem(134);
  @include mq("sp") {
    width: 100%;
    padding: rem(177) rem(15) rem(177) rem(20);
    margin-top: rem(50);
  }
}

.footer__text {
  color: $white;
  font-size: rem(26);
  font-weight: bold;
}

.footer__icons {
  display: flex;
  justify-content: flex-end;
  gap: rem(30);
  margin-top: rem(24);
  @include mq("sp") {
    display: none;
  }
}

.footer__icon {
  width: rem(62);
}

.footer__bottom {
  height: rem(135);
  padding-top: rem(43);
  @include mq("sp") {
    padding: rem(43) rem(45) 0 rem(30);
    height: rem(200);
  }
}

.footer__copyright {
  font-size: rem(22);
  text-align: center;
  @include mq("sp") {
    text-align: left;
  }
}
</style>