<script setup >


const banners = [
  {
    path: "cali.png",
    links: {
      fb: "https://www.facebook.com/profile.php?id=100063347611763&locale=it_IT"
    }
  },
  {
    path: "circuit.png",
    links: {

    }
  },
  {
    path: "karate.png",
    links: {
      fb: "https://www.facebook.com/shoreikanperugia?locale=it_IT",
      ig: "https://www.instagram.com/shoreikanperugia/"
    }
  },
  {
    path: "kick.png",
    links: {
      yt: "https://youtube.com/@onikickboxingperugia1329",
      ig: "https://www.instagram.com/oni_kickboxing_perugia/",
    }
  },
  {
    path: "ninjutsu.png",
    links: {
      ig: "https://instagram.com/ninjutsu_shibukan?igshid=YmMyMTA2M2Y=",
      fb: "https://www.facebook.com/profile.php?id=100063795812874"
    }
  },

]
let currentBanner = ref(-1);
let interval = null;

function changeActiveBanner() {
  currentBanner.value = currentBanner.value + 1;
  currentBanner.value = currentBanner.value % 5;
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
    <div class="courses-container">
      <div v-for="(banner, i) in banners" class="banner-element">
        <div class="img" :class="{ active: currentBanner == i }">
          <img class="image" :src="'courses-banner/' + banner.path" alt="">
          <div v-if="banner.links" class="links-section">
            <a v-if="banner.links.ig" :href="banner.links.ig" target="_blank"><font-awesome-icon
                icon="fa-brands fa-instagram" class="icon" /></a>
            <a v-if="banner.links.yt" :href="banner.links.yt" target="_blank"><font-awesome-icon
                icon="fa-brands fa-youtube" class="icon" /></a>
            <a v-if="banner.links.fb" :href="banner.links.fb" target="_blank"><font-awesome-icon
                icon="fa-brands fa-facebook" class="icon" /></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.links-section {
  position: absolute;
  top: 55%;
  /* left: -50%; */
  height: 130px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-direction: column;
}

a>* {
  color: white;
  width: 30px;
  height: 30px;
}

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
  position: relative;
  height: inherit;
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