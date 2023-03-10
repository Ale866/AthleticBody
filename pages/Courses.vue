<script setup>

const courses = ref([
  {
    name: "kick boxing",
    path: "kick.png",
    innerPath: 'kickboxing-course.png',
    referent: {
      name: "nome nome cognome",
      phone: '+39 123 456 7890'
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "calisthenics",
    path: "cali.png",
    innerPath: 'calisthenics-course.jpg',
    referent: {
      name: "nome nome cognome",
      phone: '+39 123 456 7890'
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "ginnastica dolce",
    path: "ginn.png",
    innerPath: 'dance-course.jpg',
    referent: {
      name: "nome nome cognome",
      phone: '+39 123 456 7890'
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "karate",
    path: "karate.png",
    innerPath: 'karate-course.png',
    referent: {
      name: "nome nome cognome",
      phone: '+39 123 456 7890'
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "circuit training",
    path: "circuit.png",
    innerPath: 'circuit-training-course.jpg',
    referent: {
      name: "nome nome cognome",
      phone: '+39 123 456 7890'
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "personal training",
    path: "pt.png",
    innerPath: '',
    referent: {
      name: "nome nome cognome",
      phone: '+39 123 456 7890'
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
  {
    name: "ninjutsu",
    path: "ninjutsu.jpg",
    innerPath: 'ninjutsu-course.png',
    referent: {
      name: "nome nome cognome",
      phone: '+39 123 456 7890'
    },
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?"
  },
])

let open = ref(false);
let currentCourse = ref({})

function openDialog(course) {
  currentCourse.value = course
  open.value = true
}

function closeDialog() {
  open.value = false
}

</script>

<template>
  <!-- <NuxtLink class="abs" to="/"><Button text="torna indietro"></Button></NuxtLink> -->
  <div class="container">
    <ModalDialog :open=open @close="closeDialog()">
      <div class="modal-container">
        <div class="exit" @click="closeDialog()">
          <font-awesome-icon icon="fa-solid fa-x" />
        </div>
        <div class="title">{{ currentCourse.name }}</div>
        <div class="content">
          <div class="info">
            <div class="description">{{ currentCourse.desc }}</div>
            <div class="referent-info">
              <h2>Per maggiori informazioni</h2>
              <div>
                <h3 class="referent-name">{{ currentCourse.referent.name }}</h3>
                <div class="referent-phone"><font-awesome-icon icon="fa-solid fa-phone" class="icon" />{{
                  currentCourse.referent.phone }}</div>
              </div>
            </div>
          </div>
          <div class="right">
            <div class="img"><img :src="'courses-detail/' + currentCourse.innerPath" alt=""></div>
          </div>
        </div>
      </div>
    </ModalDialog>
    <div class="header">
      <NuxtLink to="/"> <img class="logo" src="logo-150x150.png" alt=""> </NuxtLink>
      <h1>Corsi a disposizione</h1>
      <h4>Clicca su un qualsiasi corso per avere ulteriori informazioni</h4>
    </div>
    <div class="courses-container">
      <div class="course-element" v-for="course in courses" :key="course" @click="openDialog(course)">
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

.exit {
  position: absolute;
  top: -10px;
  right: -10px;
  background-color: red;
  width: 30px;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 100%;
  color: white;
  cursor: pointer;
  /* text-align: center;
  vertical-align: bottom; */
}

.exit > *{
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  background-color: var(--cyan);
  width: 100%;
  min-height: 100%;
  display: flex;
  justify-content: center;

  flex-direction: column;
  gap: 100px;
}

.modal-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  flex-direction: column;
  gap: 10px;
}

.info {
  width: 50%;
  height: 100%;
}

h2 {
  text-align: center;
  margin: 0;
}


.img {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  object-fit: contain;
}

.img>img {
  width: 70%;
  /* height: 90%; */
  height: auto;
  max-height: 90%;
}

@media (width <=1000px) {
  .referent-info {
    width: 200%;
  }
}

.right {
  width: 50%;
  height: 100%;
}

.title {
  width: 100%;
  height: 10%;
  color: var(--blue);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
  margin-bottom: 40px;
  margin-top: 10px;
}

.content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  height: 90%;
}

.description {
  height: 60%;
  text-align: center;
  padding: 0 25px;
  line-height: 20px;
  text-transform: none;
}

.referent-info {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-direction: column;
  height: 30%;
}

.icon {
  width: 25px;
  height: 25px;
  margin-right: 15px;
  color: var(--blue);
}

.referent-phone {
  height: 40%;
  vertical-align: middle;
  display: flex;
  align-items: center;

}

.referent-info>div {
  height: 60%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
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
  flex: 20%;
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