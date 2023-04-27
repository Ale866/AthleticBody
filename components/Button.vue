<script setup>
const props = defineProps(['text'])

</script>

<template>
  <button class="button-slide slide-right"> {{ text }}</button>
</template>

<style scoped>
button {
  background: none;
  border: 2px solid;
  font: inherit;
  line-height: 1;
  padding: 1em 2em;
  color: var(--blue);
  transition: 0.25s;
}

.button-slide {
  color: black;
  border: 2px solid var(--blue);
  /* border-radius: 14px; */
  padding: 18px 36px;
  letter-spacing: 1px;
  cursor: pointer;
  box-shadow: inset 0 0 0 0 var(--blue);
  -webkit-transition: ease-out 0.8s;
  -moz-transition: ease-out 0.8s;
  transition: ease-out 0.8s;
  text-transform: uppercase;
}

.slide-right:hover {
  box-shadow: inset 400px 0 0 0 var(--blue);
  color: white;
}
</style>