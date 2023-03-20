<script setup>

let show = ref(false);
onMounted(() => {
  setTimeout(() => {
    show.value = false
  }, 10000);
});

</script>

<template>
  <transition name="modal">
    <div class="warning" v-if="show">
      Attenzione! Si informano gli utilizzatori che la palestra rimarrà chiusa dall'1 gennaio al 31 dicembre 2023!
    </div>
  </transition>
</template>

<style scoped>
.warning {
  position: relative;
  width: 60%;
  height: 100%;
  background-color: rgb(185, 33, 33);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Inter", Sans-serif;
  border-radius: 15px;
  font-size: 16px;
  text-align: center;
}

@media (width <=600px) {
  .warning{
    text-transform: none;
    font-size: 14px;
  }
}


.modal-leave-active {
  animation: modal 0.3s ease-in reverse;
}

.modal-enter-active {
  animation: modal 0.3s ease-out;
}

@keyframes modal {
  from {
    opacity: 0;
    transform: translateY(-50px) scale(0.8);
  }

  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

</style>