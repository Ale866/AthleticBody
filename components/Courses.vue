<script setup>
let clientWidth = ref(0);

const courseWidth = 320;

let numElements = ref(0);

let currentCourses = ref([]);
let previousNumElements = 0;
let currentSliceValue = 5;
let coursesNumber = 6; //6 corsi ma partono da indice 0, per fare lo slice è uno in meno

const staff = {
  piro: {
    name: "fabrizio piro",
    path: "piro.png",
    // phone: "1234567890",
  },
  bartocci: {
    name: "giacomo bartocci",
    path: "",
  },
  tomei: {
    name: "riccardo tomei",
    path: "tomei.png",
  },
  corrado: {
    name: "davide corrado",
    path: "corrado.png",
  },
  monachino: {
    name: "gian mario monachino",
    path: "monachino.png",
  },
  bellillo: {
    name: "erika bellillo",
    path: "bellillo.jpg",
  },
  stinchi: {
    name: "claudio stinchi",
    path: "stinchi.jpg",
  },
  rinaldi: {
    name: "francesca rinaldi",
    path: "rinaldi.png",
  },
  zambrotta: {
    name: "rosa zambrotta",
    path: "zambrotta.png",
  },
};

// const staff = ref([
//   {
//     name: "fabrizio piro",
//     path: "piro.png",
//     attributes: ["kick boxing", "personal trainer", "circuit trainer"],
//   },
//   {
//     name: "giacomo bartocci",
//     path: "",
//     attributes: ["calisthenics"],
//   },
//   {
//     name: "riccardo tomei",
//     path: "tomei.png",
//     attributes: ["calisthenics", "personal trainer"],
//   },
//   {
//     name: "davide corrado",
//     path: "corrado.png",
//     attributes: ["calisthenics"],
//   },
//   {
//     name: "gian mario monachino",
//     path: "monachino.png",
//     attributes: ["ninjutsu"],
//   },
//   {
//     name: "erika bellillo",
//     path: "bellillo.jpg",
//     attributes: ["kick boxing"],
//   },
//   {
//     name: "claudio stinchi",
//     path: "stinchi.jpg",
//     attributes: ["karate"],
//   },
//   {
//     name: "francesca rinaldi",
//     path: "rinaldi.png",
//     attributes: ["personal trainer"],
//   },
//   {
//     name: "rosa zambrotta",
//     path: "zambrotta.png",
//     attributes: ["personal trainer"],
//   },
// ]);

const courses = ref([
  {
    name: "kick boxing",
    path: "kick.png",
    innerPath: "kickboxing-course.png",
    referent: [
      staff.piro,
      staff.bellillo
    ],
    desc: "La Kick Boxing o kickboxing è uno sport da combattimento che trova le sue origini in Giappone, da dove poi si è diffuso fino ad arrivare negli USA. La disciplina combina le tecniche di calcio tipiche delle arti marziali orientali ai colpi di pugno, prerogativa del pugilato occidentale.  La KICKBOXING si configura come uno sport che può essere praticato da tutti, giovani, giovanissimi ed adulti di ogni età, migliorandone la forza e l'elasticità fisica ed accrescendone la sicurezza di sé. Ottimo rimedio contro lo stress, l’allenamento della kick boxing è intenso e dinamico svolgendo così un’ottima funzione cardiovascolare, che stimola un conseguente miglioramento della resistenza e della tonicità di tutti i distretti del corpo. ",
  },
  {
    name: "calisthenics",
    path: "cali.png",
    innerPath: "calisthenics-course.jpg",
    referent: [
      staff.tomei,
      staff.bartocci,
      staff.corrado
    ],
    desc: "Il Calisthenics è un tipo di allenamento a corpo libero che permette di migliorare forza, coordinazione e composizione corporea, imparando moltissimi esercizi, da semplici ad avanzati. Grazie a un allenamento funzionale che coinvolge tutti i distretti muscolari, si andrà a potenziare la parte superiore del corpo, senza tralasciare quella inferiore. Inoltre, il Calisthenics sviluppa flessibilità, mobilità articolare e agilità lavorando anche su tutti questi aspetti. Il Calisthenics è un tipo di allenamento che sfrutta il proprio peso corporeo come resistenza, per costruire muscoli e forza.  La disciplina prevede il raggiungimento di skills (abilità) più o meno complesse. Per poterle “conquistare” si devono padroneggiare alla perfezione gli esercizi di base ed è, anche per questo, che è un allenamento perfetto per i principianti perché prevede un lavoro progressivo. Indipendentemente dal livello attuale, ci sono esercizi di Calisthenics adatti alle esigenze di tutti. Vieni a provare!",
  },
  {
    name: "karate",
    path: "karate.png",
    innerPath: "karate-course.png",
    referent: [
      staff.stinchi
    ],
    desc: "La Shōrei-Kan, “Scuola della Cortesia e delle Buone Maniere”, è stata fondata nel 1954 a Okinawa, luogo di nascita del karate, dal M° Toguchi Seikichi, allievo diretto del fondatore dello stile Gōjū-Ryū M° Miyagi Chōjun, ed è tra le maggiori scuole di karate al mondo. Attuale caposcuola in Europa è il M° Tamano Toshio il quale dirige stage e corsi istruttori ogni anno e in varie nazioni. Allo Heiwa-Dōjō, “il Dōjō della Pace e dell’Armonia”, si insegna il Karate-dō Gōjū-Ryū tradizionale di Okinawa. I bambini impareranno le basi divertendosi, accrescendo le abilità motorie e formando il proprio carattere mentre gli adulti inizieranno il proprio percorso di crescita e sviluppo tecnico, fisico e interiore. Shorei-Kan è autodifesa, esercizio, rispetto per il prossimo e tanto altro ancora. Vieni a provare quest’antica arte marziale e scegli la guida di un insegnante ufficiale Shorei-Kan. ",
  },
  {
    name: "circuit training",
    path: "circuit.png",
    innerPath: "circuit-training-course.jpg",
    referent: [
      staff.piro
    ],
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?",
  },
  {
    name: "personal training",
    path: "pt.png",
    innerPath: "",
    referent: [
      staff.tomei,
      staff.zambrotta,
      staff.rinaldi
    ],
    desc: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est sit blanditiis a. Excepturi quasi beatae possimus, et error at labore est asperiores impedit in aliquam, totam dolorem sint eligendi quisquam recusandae dicta enim atque. Nisi quam dolor impedit accusantium officiis natus placeat! Voluptates minima magnam enim non nemo debitis maxime?",
  },
  {
    name: "ninjutsu",
    path: "ninjutsu.jpg",
    innerPath: "ninjutsu-course.png",
    referent: [
      staff.monachino
    ],
    desc: "La Shibukan Kakushi Dojo, è una scuola di studio tradizionale del Ninjutsu. Il Ninjutsu comprende lo studio di 36 scuole giapponesi, tra cui gli studenti possono apprendere le tecniche di combattimento, la strategia, l'infiltrazione, la sopravvivenza e altre abilità tradizionali associate alla cultura giapponese dei ninja. Gli studenti imparano tecniche di combattimento a mani nude e con armi tradizionali, come il katana, il bo, hanbo, jutte, shuriken e molte altre armi. Infine, la cultura e la storia ninja sono anche studiate per comprendere appieno la filosofia e la mentalità ninja. Il Dojo offre ai loro studenti molti benefici, tra cui l'aumento della forza fisica, della flessibilità e dell'equilibrio, nonché lo sviluppo dell'autodisciplina, della fiducia in se stessi e del rispetto per gli altri. Gli studenti imparano anche come difendersi in situazioni di pericolo e come gestire lo stress e l’ansia. Il Dojo (luogo di allenamento) è inclusivo e accogliente, dove studenti di tutte le età e di tutti i livelli di esperienza possono apprendere e migliorare le loro abilità marziali e la loro salute mentale e fisica.",
  },
]);

let open = ref(false);
let currentCourse = ref({});

function openDialog(course) {
  currentCourse.value = course;
  open.value = true;
}

function closeDialog() {
  open.value = false;
}

function onScreenResize() {
  window.addEventListener("resize", () => {
    updateScreenWidth();
  });
}

function updateScreenWidth() {
  clientWidth.value = window.innerWidth;
  numElements.value = Math.trunc(clientWidth.value / courseWidth);
  if (numElements.value > 5) {
    numElements.value = 5;
  }
  if (numElements.value != previousNumElements) {
    currentCourses.value = courses.value.slice(0, numElements.value);
  }
  previousNumElements = numElements.value;
}

onMounted(() => {
  onScreenResize();
  updateScreenWidth();
});

function advanceCourse() {
  currentCourses.value.push(courses.value[currentSliceValue]);
  currentCourses.value.shift();
  currentSliceValue++;
  currentSliceValue = currentSliceValue % coursesNumber;
}

function decreaseCourse() {
  currentCourses.value.pop();
  currentCourses.value.unshift(courses.value[currentSliceValue]);
  currentSliceValue--;
  if (currentSliceValue < 0) {
    currentSliceValue = coursesNumber - 1;
  }
}
</script>

<template>
  <!-- <NuxtLink class="abs" to="/"><Button text="torna indietro"></Button></NuxtLink> -->
  <div class="container">
    <ModalDialog :open="open" @close="closeDialog()">
      <div class="modal-container">
        <div class="exit" @click="closeDialog()">
          <font-awesome-icon icon="fa-solid fa-x" />
        </div>
        <div class="title">{{ currentCourse.name }}</div>
        <div class="content">
          <div class="info">
            <div class="description">{{ currentCourse.desc }}</div>
            <div class="referent-info">
              <div v-for="referent in currentCourse.referent" :key="index">
                <img class="referent-image" :src="'staff/' + referent.path" />
                <div class="name">
                  {{ referent.name }}
                </div>
                <div class="phone-number">{{ referent.phone }}</div>
              </div>
              <div>
                <h3 class="referent-name">{{ currentCourse.referent.name }}</h3>
                <div class="referent-phone">
                  <font-awesome-icon icon="fa-solid fa-phone" class="icon" />{{
                    currentCourse.referent.phone
                  }}
                </div>
              </div>
            </div>
          </div>
          <div class="right">
            <div class="img">
              <img :src="'courses-detail/' + currentCourse.innerPath" alt="" />
            </div>
          </div>
        </div>
      </div>
    </ModalDialog>
    <div class="header">
      <h1>Corsi a disposizione</h1>
      <h4>Clicca su un qualsiasi corso per avere ulteriori informazioni</h4>
    </div>
    <div class="courses-container">
      <button class="slideButton" @click="decreaseCourse">
        <font-awesome-icon icon="fa-solid fa-chevron-left" />
      </button>
      <div
        class="course-element"
        v-for="course in currentCourses"
        :key="course"
        @click="openDialog(course)"
      >
        <div>
          <img
            class="course-image"
            :src="'courses-img/' + course.path"
            alt=""
          />
          <h3 class="course-name">{{ course.name }}</h3>
        </div>
      </div>
      <button class="slideButton" @click="advanceCourse">
        <font-awesome-icon icon="fa-solid fa-chevron-right" />
      </button>
    </div>
  </div>
</template>

<style scoped>
.logo {
  filter: invert(76%) sepia(96%) saturate(1485%) hue-rotate(204deg)
    brightness(98%) contrast(89%);
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
}

.exit > * {
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  background-color: var(--cyan);
  width: 100%;
  height: 70%;
  display: flex;
  justify-content: space-evenly;
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

.img > img {
  width: 60%;
  height: auto;
  max-height: 90%;
}

@media (width <=1200px) {
  .referent-info {
    width: 200%;
    justify-content: flex-end;
  }
}

@media (width <=1000px) {
  .right {
    display: none;
  }

  .info {
    width: 100%;
    display: flex;
    flex-direction: column;
    flex-direction: column;
    justify-content: space-between;
  }

  .referent-info {
    width: 100%;
    justify-content: flex-end;
  }

  div.referent-info > div {
    height: 40%;
  }

  div.description {
    font-size: 0.85rem;
    padding: 0;
    margin-top: -25px;
  }
}

h2 {
  font-size: 20px;
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
  margin-bottom: 25px;
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
  font-size: 0.9rem;
  height: 60%;
  text-align: center;
  padding: 0 15px;
  line-height: 16px;
  text-transform: none;
}

.referent-info {
  display: flex;
  justify-content: flex-end;
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

.referent-info > div {
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
  text-align: center;
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
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  align-self: center;
  /* flex-wrap: wrap; */
  row-gap: 75px;
  padding-bottom: 50px;
}

.slideButton {
  height: 200px;
  width: 100px;
  background-color: transparent;
  border: none;
}

.slideButton > * {
  height: 10%;
}

.course-element > div {
  display: flex;
  flex-direction: column;
}

.course-element > div:hover {
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

.referent-info {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.referent-image {
  width: 100px;
  height: 100px;
}
</style>
