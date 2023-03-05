<script>
</script>

<template>
  <div class="main-section">
    <div class="info-section">
      <div>
        <div class="title">Chi siamo</div>
        <div class="info-content">
          <h1>Athletic body club</h1>
          <div class="text"> La palestra a Perugia Athletic Body Club nasce nel lontano 1988 e si configura subito come un
            punto di riferimento per tutti gli amanti dello sport e del benessere, nel corso degli anni ha sempre operato
            con professionalità e profondo rispetto dei suoi soci, focalizzandosi nella ricerca delle migliori metodiche
            di allenamento e seguendo le continue innovazioni che da sempre caratterizzano il settore
          </div>
        </div>
      </div>
      <div>
        <div class="title">I nostri orari</div>
        <div class="timetables-content">
          <div><font-awesome-icon icon="fa-solid fa-clock" class="icon" />
            <div><strong>lun - mar - giov: </strong>9:30-13:00 / 16:00-22:00</div>
          </div>
          <div><font-awesome-icon icon="fa-solid fa-clock" class="icon" />
            <div><strong>mer - ven: </strong>16:00-22:00</div>
          </div>
          <div><font-awesome-icon icon="fa-solid fa-clock" class="icon" />
            <div><strong>sab: </strong>9:30-13:00</div>
          </div>
        </div>
      </div>
      <div class="iframe">
        <div class="title">Dove trovarci</div>
        <ClientOnly>
          <iframe frameborder="0" referrerpolicy="no-referrer-when-downgrade"
            src="https://maps.googleapis.com/maps/embed/v1/place?key=AIzaSyBnEjUO5AIQG5laeY3UeUX5PJshfiV383M&q=Athletic+Body+Ssd"
            allowfullscreen>
          </iframe>
        </ClientOnly>
      </div>
    </div>
    <div class="img-container">
      <img src="/poweredBy.png" alt="">
    </div>
    <div class="left">
    </div>


    <div class="right">

    </div>
  </div>
</template>

<style scoped>
.main-section {
  display: flex;
  /* justify-content: space-evenly; */
  align-items: flex-start;
  flex-direction: row;
  width: 100%;
  height: 100%;
  margin-top: 40px;
}

/* .main-section>div {
  width: 100%;
  display: flex;
  align-items: flex-start;
  height: 100%;
} */

.info-section {
  width: 50%;
  display: flex;
  justify-content: space-evenly;
  align-items: flex-start;
  flex-direction: column;
  margin-left: 45px;
  height: 100%
}

.info-section>div {
  width: 100%;
}

.title {
  font-size: 24px;
  color: var(--blue);
}

.text {
  color: var(--gray);
  text-transform: none;
  font-size: 17px;
  font-weight: 400;
  line-height: 20px;
}

.timetables-content {
  margin-top: 30px;
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 20px;
}

.timetables-content>div {
  width: 100%;
  display: flex;
  align-items: center;
}

.timetables-content>div>.icon {
  width: 25px;
  height: 25px;
  margin-right: 8px;
  color: var(--blue);
}

.timetables-content>div>div {
  font-size: 18px;
  color: var(--gray);
}

.iframe {
  height: 40%;
}

iframe {
  width: 100%;
  height: 100%;
  margin-top: 30px;
}

.img-container {
  display: grid;
  place-items: center;
  justify-items: end;
}

img {
  width: 80%;
  /* scale: 0.5; */
}

@media (width <= 1024px) {
  .main-section {
    flex-direction: column;
    gap: 50px;
  }

  .info-section{
    width: 90%;
    margin-left: 5%;
    gap: 40px;
  }

  .img-container{
    width: 100%;
    justify-items: center;
    margin-top: 40px;
  }
}
</style>