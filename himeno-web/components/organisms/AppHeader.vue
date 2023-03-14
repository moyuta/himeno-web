<template>
  <header class="header">
    <nav class="header__nav">
      <ul class="header__list">
        <li class="header__item">
          <NuxtLink to="/">ホーム</NuxtLink>
        </li>
        <li class="header__item">
          <NuxtLink to="/about">私達について</NuxtLink>
        </li>
        <li class="header__item">
          <NuxtLink to="/reason">選ばれる理由</NuxtLink>
        </li>
        <li class="header__item">
          <NuxtLink to="/work">ワークフロー</NuxtLink>
        </li>
        <li class="header__item">
          <NuxtLink to="/faq">FAQ</NuxtLink>
        </li>
        <li class="header__item">
          <NuxtLink to="/example">事例紹介</NuxtLink>
        </li>
        <li class="header__item">
          <NuxtLink to="/company">会社概要</NuxtLink>
        </li>
        <li class="header__item">
          <NuxtLink to="/contact">お問合せ・お見積</NuxtLink>
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
            <li class="drawer__item">
              <NuxtLink to="/">ホーム</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/about">私達について</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/reason">選ばれる理由</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/work">ワークフロー</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/faq">FAQ</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/example">事例紹介</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/company">会社概要</NuxtLink>
            </li>
            <li class="drawer__item">
              <NuxtLink to="/contact">お問合せ・お見積</NuxtLink>
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
  </header>
</template>
<script>
</script>
<style lang="scss">
a {
  text-decoration: none;
}
nav {
  font-family: kozuka-gothic-pr6n, sans-serif;
}
li {
  list-style: none;
}
ul {
  padding: 0;
  margin: 0;
}

.header__list {
  display: flex;
  gap: 30px;
}

.drawer {
  display: none;
}

////////////////////////////
///SP用
////////////////////////////
@media screen and (max-width: 750px) {
  .header__nav {
    display: none;
  }

  .drawer {
    display: block;
  }

  #drawer__nav {
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

  #drawer__icon {
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

  #drawer__icon span {
    position: absolute;
    display: inline-block;
    width: 30px;
    height: 4px;
    background: #666666;
    right: 3px;
    transition: 0.1s ease-out;
  }
  #drawer__icon span:nth-child(1) {
    top: 6px;
  }
  #drawer__icon span:nth-child(2) {
    top: 50%;
    transform: translateY(-50%);
  }
  #drawer__icon span:nth-child(3) {
    bottom: 6px;
  }

  #drawer__cb {
    display: none;
  }

  #drawer__cb:checked ~ #drawer__nav {
    transform: translate(-100%);
  }

  #drawer__cb:checked ~ #drawer__icon span:nth-child(1) {
    top: 20px;
    transform: rotate(-45deg);
  }
  #drawer__cb:checked ~ #drawer__icon span:nth-child(2) {
    display: none;
  }
  #drawer__cb:checked ~ #drawer__icon span:nth-child(3) {
    bottom: 12px;
    transform: rotate(45deg);
  }

  .drawer__container {
    border: 1px solid #333;
    padding: 29.5px 50px 61.5px 38px;
    max-width: 334px;
    margin: auto;
    box-sizing: border-box;
  }

  .drawer__item a {
    color: #333;
    font-size: 22px;
  }
  .drawer__icons {
    display: flex;
    margin-top: 53px;
    gap: 8%;
  }
  .drawer__icon {
    width: 70px;
    flex-shrink: 0;
  }
}
</style>
