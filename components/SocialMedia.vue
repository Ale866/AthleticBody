<script setup>

</script>

<template>
  <div class="social-container">
    <div><a href="https://www.instagram.com/athleticbodyclub/" target="_blank"><font-awesome-icon
          icon="fa-brands fa-instagram" class="icon" /></a> </div>
    <div><a href="https://www.facebook.com/palestraathleticbodyclub/?locale=it_IT" target="_blank">
        <font-awesome-icon icon="fa-brands fa-facebook" class="icon" />
      </a> </div>
  </div>
</template>

<style scoped>
.social-container {
  position: absolute;
  width: 75px;
  height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
}

.social-container>div {
  width: 40%;
  height: 100%;
}

.social-container>div>a>* {
  width: 100%;
  height: 100%;
}

a {
  all: unset;
  cursor: pointer;
}
</style>