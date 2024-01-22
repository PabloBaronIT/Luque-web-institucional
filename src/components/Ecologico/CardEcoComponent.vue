<template>
  <div class="eco-contenedor">
    <div class="medio">
      <div>
        <img src="@/assets/images/EcoLogo.svg" alt="" class="logo" />
      </div>
      <div class="text">
        <h3>¡POR UN PLANETA MÁS VERDE!</h3>
        <p>
          La digitalización es la clave para proteger nuestro planeta. Al
          reducir el uso de papel y adoptar tecnologías ecoamigables podemos
          hacer del mundo un lugar más verde y limpio.
        </p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "CardEcoComponent",
};
</script>
<style scoped>
.eco-contenedor {
  background: #3bae49;
  color: white;
  /* height: 5%; */
  max-height: 169px;
  width: 75%;
  margin: auto;
  border-radius: 0px 50px;
  margin-top: 3%;
  padding: 1rem;
}
.medio {
  width: 95%;
  height: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  margin: auto;
}
.logo {
  min-height: 130px;
  min-width: 130px;
  margin-left: 16%;
}
.text {
  text-align: left;
  width: 78%;
}
.text p {
  font-size: 21px;
  margin-top: -0.7rem;
  font-weight: 100;
}
.text h3 {
  font-weight: 700;
  letter-spacing: 1px;
}
</style>
