<template>
  <div class="welcome_msg">
    <div class="welcome_msg_box">
      <!-- Welcome Message -->
      <span class="welcome_msg_txt"
        >Welcome on SIECLE Paris new website, enjoy your visit !</span
      >

      <!-- Right Side Controls -->
      <div class="langauge_box">
        <!-- Language Selector -->
        <select v-model="selectedLanguage" class="language">
          <option value="en">English</option>
          <option value="fr">Français/option></option>
        </select>

        <!-- Currency Selector -->
        <select v-model="selectedCurrency" class="language">
          <option value="eur">Euro (€)</option>
          <option value="usd">USD ($)</option>
          <option value="gbp">GBP (£)</option>
        </select>

        <!-- Links -->
        <div class="links">
          <a href="#" class="Meet_us">Meet us</a>
          <a href="#" class="customer_service">Customer service</a>
        </div>
      </div>
    </div>
  </div>

  <div class="top-header">
    <div class="main_header">
      <input type="text" placeholder="I'm looking for..." class="search" />

      <button class="search_icon">
        <i class="fa fa-search"></i>
      </button>
    </div>

    <div class="img_container">
      <img
        src="C:\Users\tommy\Desktop\Vue-Sielie\my-vue-app\src\assets\images\siecle-paris-logo.jpg"
        alt=""
        class="logo_image"
      />

      <div class="info">
        <a href="#" class="login">
          <i class="fa fa-user"></i><span>Login</span>
        </a>
        <a href="#" class="cart">
          <i class="fa fa-shopping-cart"></i><span>Shopping cart</span>
        </a>
      </div>
    </div>
  </div>

  <!-- Right -->
</template>

<script setup>
import { ref } from "vue";

const selectedLanguage = ref("en");
const selectedCurrency = ref("eur");
</script>

<style scoped>
.welcome_msg {
  width: 100vw;
  height: 4vh;
  background-color: #4b2a59;
  white-space: nowrap;
  overflow-x: auto;
  align-items: center; /* vertically center children */

  position: absolute;
  top: 2%;
  left: 0;
  transform: translateY(-50%);
}

.welcome_msg * {
  display: inline;
}

.welcome_msg_txt {
  color: white;
  font-size: 14px;
  position: relative; /* allows top to work */
  left: -15%;
  top: 10%; /* move text down 4% of its container's height */
  font-weight: 400;
}

.language {
  padding: 5px 10px 5px 8px; /* space for text and custom arrow */
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 3px; /* rounded corners */
  background-color: #fff;
  color: #333;
  cursor: pointer;
  outline: none;

  overflow-x: auto;
  align-items: center; /* vertically center children */

  position: relative;
  top: 7%;
  right: -10%;

  position: relative;
}

.langauge_box select:first-of-type {
  margin-right: 10px; /* only adds space after the first dropdown */
}

.links {
  position: relative;
  right: -12%;
  top: 10%;
}

.Meet_us {
  color: white;
  margin-right: 10px;
  font-size: 14px;
  font-weight: 400;
}

.customer_service {
  color: white;
  font-size: 14px;
  font-weight: 400;
}

.main_header {
  display: flex;
  align-items: center;
  max-width: 450px; /* adjust as needed */
  position: relative;
  margin-top: 2%;
  z-index: 10; /* keeps it above the image section */
  left: 15%;
}

.search {
  flex: 1;
  padding: 10px 15px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-right: none; /* removes right border so it connects with button */
  border-radius: 4px 0 0 4px; /* rounded left corners only */
  outline: none;
  background-color: #fff;
  color: #333;
}

.search:focus {
  border-color: #999; /* darker border on focus */
  box-shadow: 0 0 5px rgba(75, 42, 89, 0.9);
}

.search_icon {
  padding: 10px 15px;
  background-color: #fff;
  border: 1px solid black;
  border-radius: 1px 4px 4px 1px; /* rounded right corners only */
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #333;
  transition: background-color 0.2s;
}

.search_icon:hover {
  background-color: #f5f5f5;
}

.search_icon i {
  font-size: 16px;
}

.img_container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: -50px; /* adjust the value to push it up more or less */
  z-index: 10; /* keeps it above the image section */
}

.logo_image {
  width: 8%;
  height: auto;
  margin-left: 10%;
  z-index: 10; /* keeps it above the image section */
}

.info {
  position: relative;
  right: -15%;
  z-index: 10; /* keeps it above the image section */
}

.login {
  color: black;
  margin-right: 10px;
  font-size: 16px;
  font-weight: 400;
  justify-content: space-between;
  gap: 20px;
}

.cart {
  color: black;
  font-size: 16px;
  font-weight: 400;
}

.cart i {
  margin-right: 5px;
}

.login i {
  margin-right: 5px;
}

.top-header {
  position: fixed; /* change to fixed */
  top: 4vh; /* position right below welcome_msg (4vh is the height) */
  left: 0;
  right: 0;
  z-index: 99; /* below welcome_msg but above content */
  background-color: white; /* add background so content doesn't show through */
  padding: 10px 0; /* optional padding */
}
</style>
