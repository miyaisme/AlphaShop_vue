<template>
  <div id="app">
    <nav id="navbar" class="navbar d-flex justify-content-center fixed-top">
      <div class="logo">
        <img src="https://i.imgur.com/zIfk9QX.png" alt="#" class="image-logo" />
      </div>
      <div
        id="navbar-list"
        class="
          list
          d-flex
          justify-content-between
          position-fixed
          w-100
          align-items-center
        "
      >
        <ul class="menu-list">
          <li class="menu-item">男款</li>
          <span class="menu-item-border"></span>
          <li class="menu-item">女款</li>
          <span class="menu-item-border"></span>
          <li class="menu-item">最新消息</li>
          <span class="menu-item-border"></span>
          <li class="menu-item">聯絡我們</li>
          <span class="menu-item-border"></span>
          <li class="menu-item">課製商品</li>
          <span class="menu-item-border"></span>
        </ul>
        <div class="icons d-flex justify-content-end">
          <img
            src="https://i.imgur.com/Ju92vGZ.png"
            alt="#"
            class="icon-item"
          />
          <img
            src="https://i.imgur.com/BOYnOmT.png"
            alt="#"
            class="icon-item"
          />
          <img
            src="https://i.imgur.com/tLA3YpE.png"
            alt="#"
            class="icon-item"
          />
        </div>
      </div>
    </nav>
    <main>
      <router-view/>
    </main>
    <footer id="footer-content" class="footer d-flex fixed-bottom">
      <div class="footer-wrapper d-flex justify-content-between">
        <div class="footer-logo">
          <img
            src="https://i.imgur.com/zIfk9QX.png"
            alt="#"
            class="image-logo"
          />
        </div>
        <div class="footer-item">
          <h4 class="client-servise">客戶服務</h4>
          <div class="servise">運送說明</div>
          <div class="servise">退換貨相關</div>
          <div class="servise">付款資訊</div>
          <div class="servise">FAQ</div>
        </div>
        <div class="footer-item">
          <h4 class="abouts">關於我們</h4>
          <div class="about">品牌故事</div>
          <div class="about">媒體連繫</div>
          <div class="about">Press kit</div>
        </div>
        <div class="footer-item">
          <h4 class="information">資訊</h4>
          <div class="footer-info">隱私權政策</div>
          <div class="footer-info">Cookie</div>
          <div class="footer-info">GDPR</div>
        </div>
        <div class="footer-item">
          <h4 class="contacts">追蹤 ALPHA Shop</h4>
          <div class="contact">+886 02123-45678</div>
          <div class="footer-icons">
            <div class="footer-icon fb fab fa-facebook-f"></div>
            <div class="footer-icon fab fa-instagram"></div>
            <div class="footer-icon fas fa-phone"></div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import "bootstrap";
import "bootstrap/dist/css/bootstrap.min.css";
export default {};
</script>

<style lang="scss">
/* reset css */
body {
  margin: 0;
  padding: 0;
}
* {
  box-sizing: border-box;
}
h1,
h2,
h3,
h4,
h5,
h6,
p {
  margin: 0px;
  padding: 0px;
}
ul,
ol,
li {
  list-style: none;
  margin: 0px;
  padding: 0px;
}
a,
a:hover,
a:focus {
  text-decoration: none;
}
img {
  width: 100%;
  height: 100%;
  display: block;
}
.btn,
button,
button:focus,
input:focus,
textarea:focus,
select,
select:focus,
a:focus {
  outline: 0px !important;
}
button {
  background-color: transparent;
  border: 0;
  cursor: pointer;
}
button[disabled] {
  pointer-events: none;
}
input {
  padding: 0;
}
input:required {
  box-shadow: none;
}
input:invalid {
  box-shadow: none;
}
input[type="text"] {
  font-size: 12px;
  padding-left: 16px;
  color: #999999;
}
input[type="radio"] {
  width: 20px;
  height: 20px;
  margin: 26px;
  border: 1px solid black;
  border-radius: 50%;
  -webkit-appearance: none;
  /* for webkit browsers */
  -moz-appearance: none;
  /* for firefox */
  appearance: none;
}
input[type="radio"]:checked {
  border: 6px solid black;
}
select {
  font-size: 12px;
  color: #999999;
  padding-left: 16px;
  overflow: hidden;
  background-color: transparent;
  -webkit-appearance: none;
  /* for webkit browsers */
  -moz-appearance: none;
  /* for firefox */
  appearance: none;
  /* for modern browsers */
}
select optgroup {
  font-size: 12px;
}
/* basic setting */
$body-bg: rgb(255, 255, 255);
$body-color: #000000;
$white: #fff;
$black: #000000;
$pink: #f67599;
$gray: #f0f0f5;
/* css style */
#app {
    width: 1440px;
    margin: 0 auto;
}
#navbar {
  background-color: white;
}
#footer-content {
    background-color: #f0f0f5;
}
.menu-list {
    margin-left: 165px;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    width: 20%;
}
.menu-item {
  margin: 1rem 0;
}
.icons {
    margin-right: 165px;
    justify-content: flex-end;
}
.icon-item {
  margin: 0 1.5rem;
}
.footer-wrapper {
  margin: 0 165px;
  padding: 2.5rem 0;
}
.image-logo {
    width: 136px;
    height: 24px;
}
.icon-item {
    width: 24px;
    height: 24px;
}
</style>