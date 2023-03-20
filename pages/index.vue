<script setup></script>

<template>
  <div class="bg">
    <div class="container">
      <div class="announcement">
        <TheWaning></TheWaning>
      </div>
      <div class="social-media">
        <SocialMedia></SocialMedia>
      </div>
      <div class="img-container">
        <img src="/logo-150x150.png" alt="" />
      </div>
      <div class="title">Athletic body club</div>
      <div class="subtitle">Una palestra, tante discipline</div>
    </div>
  </div>
  <GeneralInfo></GeneralInfo>
  <!-- <div><a href="https://www.instagram.com/athleticbodyclub/" target="_blank">assadas</a></div> -->
</template>

<style scoped>
.announcement {
  position: absolute;
  top: 80px;
  width: 100%;
  height: 10%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.social-media {
  position: absolute;
  top: 10px;
  right: 100px;
  color: white;
}
.bg {
  position: relative;
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

@media (width <=600px) {
  .subtitle {
    font-size: 40px;
  }
}
</style>
