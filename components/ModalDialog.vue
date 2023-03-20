<script setup>
const props = defineProps(['open'])
const emit = defineEmits(['close'])
</script>



<template>
  <div v-if="open" class="backdrop" @click="$emit('close')"></div>
  <transition name="modal">
    <dialog open v-if="open">
      <slot></slot>
    </dialog>
  </transition>
</template>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: 10;
  background-color: rgba(0, 0, 0, 0.75);
  display: flex;
  justify-content: center;
}

dialog {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  /* top: 30vh; */
  width: 50%;
  height: 60%;
  /* margin: auto; */
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border-radius: 12px;
  padding: 1rem;
  background-color: var(--cyan);
  z-index: 100;
  border: none;
}

.modal-leave-active {
  animation: modal 0.3s ease-in reverse;
}

.modal-enter-active {
  animation: modal 0.5s ease-out;
}

@keyframes modal {
  from {
    opacity: 0;
    /* transform: translateY(-50px) scale(0.8); */
  }

  to {
    opacity: 1;
    /* transform: translateY(0) scale(1); */
  }
}

@media (width <=1250px) {
  dialog {
    width: 65%;
    height: 70%;
  }
}

@media (width <=750px) {
  dialog {
    width: 85%;
    height: 90%;
  }
}
</style>