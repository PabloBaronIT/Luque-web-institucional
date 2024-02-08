<template>
  <div class="historia-container">
    <div class="linea">
      <div class="izquierdo"></div>
      <h5>NUESTRA HISTORIA</h5>
      <div class="derecho"></div>
    </div>
    <HistoriaComponentVue />
    <div class="textoUltimo">
      <h4>
        En cada momento vivido, ha sido un hilo en la construcción del presente
        de Luque. Guiados por la historia, nos embarcamos en la tarea de labrar
        un mañana aún más robusto.
      </h4>
      <div class="volver">
        <div style="display: flex; flex-direction: row">
          <h4>Siguiente</h4>
          <router-link to="/pueblo/sacanta-hoy/#inicio">
            <img src="@/assets/images/FlechaDerecha.svg" alt="imagen" />
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HistoriaComponentVue from "@/components/Historia/HistoriaComponent.vue";
export default {
  name: "HistoriaView",
  components: {
    HistoriaComponentVue,
  },
  created() {
    window.scrollTo(0, 0);
  },
};
</script>

<style scoped>
.historia-container {
  /* margin-top: -4%; */
  /* padding-top: ; */
  width: 100%;
  margin-top: 3%;
  position: relative;
  background: #ffffff;
}

.linea {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: auto;
  /* margin-top: 7vh; */
  /* margin-bottom: 7vh; */
}

.linea h5 {
  font-weight: 600;
  color: #4b4a49;
}

.izquierdo {
  width: 40%;
  height: 1px;
  background: #4b4a49;
  margin-bottom: 1%;
}

.derecho {
  height: 1px;
  width: 40%;
  background: #4b4a49;
  margin-bottom: 1%;
}
.textoUltimo {
  text-align: center;
  width: 85%;
  /* height: 146px; */
  margin: auto;
  margin-top: 5%;
  padding-bottom: 10%;
  position: relative;
}
.textoUltimo h4 {
  font-weight: 400;
  font-size: 24px;
}
.volver {
  position: absolute;
  width: 10%;
  right: 5%;
  bottom: 15%;
  /* display: flex; */
  /* flex-direction: row; */
  /* justify-content: space-between; */
  /* padding: 3.5%; */
  /* bottom: 16%; */
  /* margin: auto; */
  /* right: 4%; */
  /* left: 10%; */
}

.volver h4 {
  /* margin-left: 14px; */
  color: #4b4a49;
  font-size: 24px;
  font-style: normal;
  font-weight: 400;
  margin-top: 2.5vh;
  margin-left: 1vw;
  margin-right: 1vw;
}

@media (max-width: 500px) {
  .linea {
    /* text-align: center;
    margin-top: 3%;
    margin-bottom: 3%; */
    display: none;
  }
  .volver {
    width: 10%;
    right: 2%;
    bottom: -4%;
    /* background: red; */
  }
  .volver h4 {
    display: none;
  }
  .volver img {
    width: 32px;
    height: 32px;
  }
  .linea h5 {
    font-size: 8px;
    font-weight: 400;
  }
  .izquierdo {
    width: 30%;
  }
  .derecho {
    width: 30%;
  }
  .textoUltimo h4 {
    font-size: 12px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
  }
}
</style>
