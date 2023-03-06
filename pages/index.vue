<script setup>
import GeneralInfo from '../components/GeneralInfo.vue'
</script>

<template>
  <div class="bg">
    <div class="container">
      <div class="img-container">
        <img src="/logo-150x150.png" alt="">
      </div>
      <div class="title">Athletic body club</div>
      <div class="subtitle">Una palestra, tante discipline</div>
    </div>
  </div>
  <GeneralInfo></GeneralInfo>
  <!-- <div><a href="https://www.instagram.com/athleticbodyclub/" target="_blank">assadas</a></div> -->
</template>

<style scoped>
.bg {
  background-image: url("/bgImage.png");
  height: 100%;
  width: 100%;

  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;

  display: flex;
  justify-content: center;
  align-items: center;

  color: white;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.img-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.title {
  font-size: xx-large;
  font-weight: 600;
  text-align: center;
}

.subtitle {
  font-size: 62px;
  font-weight: 400;
  font-family: "Bebas Neue", Sans-serif;
  letter-spacing: -3px;
  text-align: center;
}
</style>