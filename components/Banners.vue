<script setup >


const banners = [
  "cali.png", "circuit.png", "karate.png", "kick.png", "ninjutsu.png"
]
let currentBanner = ref(-1);
let interval = null;

function changeActiveBanner() {
  currentBanner.value = currentBanner.value + 1;
  currentBanner.value = currentBanner.value % 5;
  console.log(currentBanner.value);
}

onMounted(() => {
  changeActiveBanner()
  tick()
})

function tick() {
  interval = setInterval(() => {
    changeActiveBanner()
  }, 5000);
}

onBeforeUnmount(() => {
  clearInterval(interval)
})

</script>

<template>
  <div class="container">
    <!-- <div class="header"> -->
    <!-- <h1>Le nostre promozioni</h1> -->
    <!-- </div> -->
    <div class="courses-container">
      <div v-for="(banner, i) of banners" class="banner-element">
        <div class="img">
          <img class="image" :src="'courses-banner/' + banner" alt="" :class="{ active: currentBanner == i }">
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 100%;
  min-height: 70%;
  display: flex;
  justify-content: space-evenly;
  flex-direction: column;
  gap: 100px;
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

.banner-element {
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

@media (width < 1500px) {
  .courses-container {
    margin-top: 30px;
  }

  .banner-element {
    flex-basis: 33%;
  }
}

.active {
  animation: aa 5s infinite;
}

@keyframes aa {
  from {
    transform: scale(1);
  }

  75% {
    transform: scale(1.2);
  }

  to {
    transform: scale(1);
  }
}
</style>