<script setup lang='ts'>
const banners = [
  "cali.png", "circuit.png", "karate.png", "kick.png", "ninjutsu.png"
]
</script>

<template>
  <div class="container">
    <!-- <div class="header"> -->
      <!-- <h1>Le nostre promozioni</h1> -->
    <!-- </div> -->
    <div class="courses-container">
      <div v-for="banner of banners" class="course-element">
        <div class="img">
          <img class="image" :src="'courses-banner/' + banner" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  /* background-color: var(--cyan); */
  width: 100%;
  height: 60%;
  display: flex;
  justify-content: space-evenly;
  flex-direction: column;
  gap: 100px;
}

.header {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.courses-container {
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  align-self: center;
  /* flex-wrap: wrap; */
  row-gap: 75px;
}

.img {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  object-fit: contain;
}

.course-element {
  /* flex: 20%; */
  height: 100%;
  display: flex;
  gap: 0;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.image{
  height: 75%;
}
</style>