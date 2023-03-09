<script setup>

const courses = ref([
  {
    name: "kick boxing",
    path: "kick.png",
    referent: {
      name: "nomenome",
      phone: 1234567890
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "calisthenics",
    path: "cali.png",
    referent: {
      name: "nomenome",
      phone: 1234567890
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "ginnastica dolce",
    path: "ginn.png",
    referent: {
      name: "nomenome",
      phone: 1234567890
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "karate",
    path: "karate.png",
    referent: {
      name: "nomenome",
      phone: 1234567890
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "circuit training",
    path: "circuit.png",
    referent: {
      name: "nomenome",
      phone: 1234567890
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "personal training",
    path: "pt.png",
    referent: {
      name: "nomenome",
      phone: 1234567890
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "ninjutsu",
    path: "ninjutsu.jpg",
    referent: {
      name: "nomenome",
      phone: 1234567890
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
])

</script>

<template>
    <!-- <NuxtLink class="abs" to="/"><Button text="torna indietro"></Button></NuxtLink> -->
  <div class="container">
    <div class="header">
      <NuxtLink to="/"> <img class="logo" src="logo-150x150.png" alt=""> </NuxtLink> 
      <h1>Corsi a disposizione</h1>
      <h4>Clicca su un qualsiasi corso per avere ulteriori informazioni</h4>
    </div>
    <div class="courses-container">
      <div class="course-element" v-for="course in courses">
        <div>
          <img class="course-image" :src="'courses-img/' + course.path" alt="">
          <h3 class="course-name">{{ course.name }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.logo {
  filter: invert(76%) sepia(96%) saturate(1485%) hue-rotate(204deg) brightness(98%) contrast(89%);
}

.container {
  background-color: var(--cyan);
  width: 100%;
  display: flex;
  justify-content: center;
  /* align-items: center; */
  /* align-items: start; */
  flex-direction: column;
  gap: 100px;
}

h1 {
  text-align: center;
}

.abs {
  position: absolute;
  top: 10px;
}

h4 {
  margin: 0;
}

.course-element {
  /* flex: 25%; */
  display: flex;
  gap: 0;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.course-name {
  height: 75px;
  width: 360;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--blue);
  margin: 0;
  color: white;
  border-radius: 0 0 15px 15px;
}

.header {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.courses-container {
  gap: 100px;
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-wrap: wrap;
  row-gap: 75px;
}

.course-element>div {
  display: flex;
  flex-direction: column;
}

.course-element>div:hover {
  animation: scale 1.5s forwards infinite;
}

@keyframes scale {
  from {
    transform: translateY(0%);
  }

  50% {
    transform: translateY(-10%);
  }

  to {
    transform: translateY(0%);
  }
}


.course-image {
  width: 250px;
  height: 200px;
  border-radius: 15px 15px 0 0;
}
</style>