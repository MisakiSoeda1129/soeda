<template>
  <div class="header">
    <div id="firstview">
      <header id="top-header">
        <div class="flex">
          <h1 class="header-logo">estra inc.</h1>
          <nav class="header-nav">
            <ul>
              <li><a href="#">home</a></li>
              <li><a href="#">about</a></li>
              <li><a href="#">service</a></li>
              <li><a href="#">works</a></li>
              <li><a href="#">price</a></li>
              <li><a href="#">contact</a></li>
            </ul>
          </nav>
        </div>
      </header>
      <p class="catchcopy">機械ではできない仕事を</p>
      <div class="news flex">
        <div class="news-content">
          <p class="news_date">2019/01/01</p>
          <p class="news_title">
            ニュースタイトルがここには入ります。3月の決算報告書
          </p>
        </div>
        <div class="news-icon">news</div>
      </div>
    </div>
    <div id="hamburger" @click="hamburgerMenuOpen" :class="{'is-active': active}">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <nav class="hamburger-menu" :class="{'is-active': active}">
      <p class="hamburger-menu__txt">estra inc.</p>
      <ul class="hamburger-menu__list">
        <li class="hamburger-menu__list-item"><a href="#">home</a></li>
        <li class="hamburger-menu__list-item"><a href="#">about</a></li>
        <li class="hamburger-menu__list-item"><a href="#">service</a></li>
        <li class="hamburger-menu__list-item"><a href="#">works</a></li>
        <li class="hamburger-menu__list-item"><a href="#">price</a></li>
        <li class="hamburger-menu__list-item"><a href="#">contact</a></li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: false
    }
  },
  methods: {
    hamburgerMenuOpen: function() {
      this.active = !this.active;
    }
  }
}
</script>

<style scoped>
  #hamburger.is-active span:nth-of-type(1) {
    top: 20px;
    transform: rotate(45deg);
  }
  #hamburger.is-active span:nth-of-type(2) {
    opacity: 0;
  }
  #hamburger.is-active span:nth-of-type(3) {
    top: 20px;
    transform: rotate(-45deg);
  }

  .hamburger-menu {
    display: block;
    width: calc(100% - 80px);
    height: 100%;
    text-align: center;
    transition: 0.2s;
    position: fixed;
    top: 0;
    left: calc(-100% - 80px);
    background: #fff;
    color: #333333;
    box-shadow: 80px 0 rgba(38, 98, 213, 0.3);
    z-index: 9999;
    transition: left 300ms;
  }
  .hamburger-menu__txt {
    margin: 40px 20px;
    font-size: 2.2rem;
    color: #333333;
    text-align: left;
    font-weight: bold;
  }
  .hamburger-menu__list-item a {
    color: #333333;
    margin: 15px;
    padding: 5px;
    border-bottom: 0.5px solid #2662d5;
    text-decoration: none;
    display: block;
  }
  .hamburger-menu__list-item {
    width: 100%;
    text-align: left;
  }
  .hamburger-menu.is-active {
    left: 0;
  }
</style>
