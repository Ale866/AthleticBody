<script setup lang='ts'>
const promotions = [
  "bring-friend-discount.jpeg",
  "students-discount.jpeg"
]
</script>

<template>
  <div class="container">
    <div class="header">
      <h1>Le nostre promozioni</h1>
    </div>
    <div class="courses-container">
      <div v-for="(promotion, i) of promotions" class="promotion-element">
        <div class="img">
          <img class="image" :src="'promotions/' + promotion" alt="promotion">
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.header {
  text-align: center;
}

.container {
  margin-top: 50px;
  width: 100%;
  min-height: 70%;
  display: flex;
  justify-content: space-evenly;
  flex-direction: column;
  background-color: var(--cyan);
}

.courses-container {
  margin-top: 30px;
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  align-self: center;
  flex-wrap: wrap;
}

.img {
  display: flex;
  justify-content: center;
  align-items: center;
  object-fit: contain;
}

.promotion-element {
  height: 100%;
  display: flex;
  gap: 0;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.image {
  height: 320px;
  margin: 30px;
}
</style>