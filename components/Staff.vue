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
  <div v-for="person in staff">
    <img :src="'staff/' + person.path">
    <div class="name">
      {{ person.name }}
    </div>
    <div v-for="attr in person.attributes">
      <div>{{ attr }}</div>
    </div>
  </div>
</template>

<style scoped>
div {}
</style>