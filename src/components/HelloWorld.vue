<script setup>
import topHeader from "./topHeader.vue";
import ChatComponent from "./ChatBotWidget.vue";
</script>

<template>
  <topHeader />

  <!-- Navigation -->
  <nav class="links2-container">
    <a href="#" class="links2">Products</a>
    <a href="#" class="links2">Styles</a>
    <a href="#" class="links2">Discover the SIÈCLE universe</a>
  </nav>
  <!-- Hero Section -->
  <section class="hero-section">
    <img
      src="C:\Users\tommy\Desktop\Vue-Sielie\my-vue-app\src\assets\images\image1.jpg"
      alt="Ceramic bowl"
    />
  </section>
  <ChatComponent />
</template>

<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css");
section {
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%); /* centers it vertically */
  width: 100%;
  overflow: hidden;
}

img {
  width: 100%;
  height: 400px;
  object-fit: cover;
  display: block;
}

.links2-container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  padding: 20px 0;
  background-color: none;
  position: absolute;
  top: 25%;
  right: 41%;
  transform: translateY(-50%); /* or fixed if you want it to stay at top */
  z-index: 100;
}

.links2 {
  color: #333;
  font-size: 14px;
  font-weight: 400;
  text-decoration: none;
  z-index: 101;
  font-weight: 500;
  font-size: 15px;
}

.links2:hover {
  text-decoration: underline;
}
</style>
