<script setup></script>

<template>
  <div class="container">
    <div class="header">
      <NuxtLink to="/">
        <img class="logo" src="logo-150x150.png" alt="" />
      </NuxtLink>
      <h1>I nostri contatti</h1>
    </div>
    <div class="contact-container">
      <div class="send-email-container">
        <div class="send-email">
          <h3 class="title">Inviaci una email</h3>
          <div class="input-container">
            <input placeholder="Nome e cognome" type="text" name="name" />
            <input placeholder="La tua email" type="text" name="email" />
            <input placeholder="Oggetto richiesta" type="text" name="subject" />
            <textarea
              placeholder="Corpo richiesta"
              type="text"
              name="name"
              rows="18"
            ></textarea>
          </div>
        </div>
      </div>
      <div class="contact-info">
        <h3 class="title left">contatti utili</h3>
        <div class="phone-container">
          <div><font-awesome-icon icon="fa-solid fa-phone" class="icon" />+39 075 37 66 818 (Fisso)</div>
          <div><font-awesome-icon icon="fa-solid fa-phone" class="icon" />+39 333 10 99 299 (Riccardo)</div>
          <div><font-awesome-icon icon="fa-solid fa-phone" class="icon" />+39 328 48 36 547 (Fabrizio)</div>
          <div class="email"><font-awesome-icon icon="fa-solid fa-envelope" class="icon" />athleticbodyclub@gmail.com</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.logo {
  filter: invert(76%) sepia(96%) saturate(1485%) hue-rotate(204deg)
    brightness(98%) contrast(89%);
}
.container {
  background-color: var(--cyan);
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

h1,
h3 {
  margin: 0;
}

.icon{
    width: 25px;
  height: 25px;
  margin-right: 15px;
  color: var(--blue);
}
.header {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.title {
  height: 10%;
  color: var(--blue);
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.contact-container {
  margin-top: 30px;
  height: 100%;
  display: flex;
}
.send-email-container {
  width: 80%;
  height: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-direction: column;
}

.send-email {
  width: 80%;
  height: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-direction: column;
}

.phone-container {
  width: 100%;
  height: 50%;
  display: flex;
  justify-content: space-evenly;
  align-items: flex-start;
  flex-direction: column;
}

.phone-container > div {
    display: flex;
    align-items: center;
    text-transform: none;
}

input,
textarea {
  width: 75%;
  border: 1px solid #666;
  border-radius: 3px;
  padding: 0.5rem 1rem;
  -webkit-transition: all 0.3s;
  -o-transition: all 0.3s;
  transition: all 0.3s;
  resize: none;
}

.left {
  justify-content: flex-start;
}

.input-container {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-direction: column;
  width: 75%;
  height: 90%;
}

input::placeholder,
textarea::placeholder {
  font-family: -apple-system, BlinkMacSystemFont, Segoe UI, Roboto,
    Helvetica Neue, Arial, Noto Sans, sans-serif;
}

.contact-info {
  width: 50%;
}
</style>
