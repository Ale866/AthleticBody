<script setup>

const staff = ref([{
  name: "fabrizio piro",
  path: "piro.png",
  attributes: ["kick boxing", "personal trainer", "circuit trainer"]
},
{
  name: "riccardo tomei",
  path: "tomei.png",
  attributes: ["calisthenics", "personal trainer"]
},
{
  name: "davide corrado",
  path: "corrado.png",
  attributes: ["calisthenics"]
},
{
  name: "gian mario monachino",
  path: "monachino.jpg",
  attributes: ["ninjutsu"]
},
{
  name: "erika bellillo",
  path: "bellillo.jpg",
  attributes: ["kick boxing"]
},
{
  name: "claudio stinchi",
  path: "stinchi.jpg",
  attributes: ["karate"]
},
{
  name: "francesca rinaldi",
  path: "rinaldi.png",
  attributes: ["personal trainer"]
},
{
  name: "rosa zambrotta",
  path: "zambrotta.png",
  attributes: ["personal trainer"]
},
{
  name: "francesca ales",
  path: "ales.png",
  attributes: ["danza orientale per il femminile"]
}
])
</script>

<template>
  <h1>Lo staff a tua disposizione</h1>
  <div class="staff-container">
    <div class="staff-element" v-for="person in staff">
      <img :src="'staff/' + person.path">
      <h3 class="name">
        {{ person.name }}
      </h3>
      <div class="members-container">
        <div class="member-info" v-for="attr in person.attributes">
          <font-awesome-icon icon="fa-solid fa-dumbbell" class="icon" />
          <div class="text">{{ attr }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
h1 {
  text-align: center;
  margin-top: 100px;
}

.text,
.name {
  text-align: center;
}

h3{
  margin-top: 10px;
}

.staff-container {
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-wrap: wrap;
  row-gap: 50px;
}

.staff-element {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  flex: 20%;
  width: 100%;
}

.members-container{
  text-transform: capitalize;
}

img {
  width: 200px;
  height: 200px;
}

.member-info {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
}

@media (width <=1260px) {
  h1{
    margin-top: 0;
  }
  .staff-container {
    justify-content: space-around;
  }

  .staff-element {
    flex: 33%;
    /* width: 30%; */
  }

}

@media (width <=1000px) {
 
  .staff-element {
    flex: 50%;
    /* width: 30%; */
  }
}</style>