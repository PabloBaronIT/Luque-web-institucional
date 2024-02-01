<template>
  <div class="contenedor-home">
    <video
      src="https://res.cloudinary.com/ddko88otf/video/upload/v1705946721/-2fac-4d53-99a3-a169717b4ac0_tnaplt.mov"
      autoplay
      loop
      muted
      type="video/webm"
    ></video>
    <TarjetasComponent />
    <div class="masGestiones">
      <p>Ingresá aquí para más gestiones</p>
    </div>
    <ImagenComponent />
    <PromocionesComponent />
    <CardEcoComponent />
    <div class="linea">
      <div class="izquierdo"></div>
      <h5>DESCUBRÍ NUESTROS PROGRAMA</h5>
      <div class="derecho"></div>
    </div>
    <GridProgramasComponent />
    <div class="linea">
      <div class="izquierdo"></div>
      <h5>TE MOSTRAMOS LAS ÚLTIMAS NOVEDADES</h5>
      <div class="derecho"></div>
    </div>
    <div class="carouselNoticias">
      <CarouselComponent />
    </div>
  </div>
</template>

<script>
// import axios from "axios";
import TarjetasComponent from "@/components/Buscador/TarjetasComponent.vue";
import ImagenComponent from "@/components/Imagen/ImagenComponent.vue";
import PromocionesComponent from "@/components/Promociones/PromocionesComponent.vue";
import CardEcoComponent from "@/components/Ecologico/CardEcoComponent.vue";
import GridProgramasComponent from "@/components/Programas/GridProgramasComponent.vue";
import CarouselComponent from "@/components/Carousel/CarouselComponent.vue";

export default {
  name: "HomeView",
  components: {
    // HelloWorld,
    TarjetasComponent,
    ImagenComponent,
    PromocionesComponent,
    CardEcoComponent,
    GridProgramasComponent,
    CarouselComponent,
  },
  data() {
    return {};
  },
  created() {},
};
</script>
<style scoped>
video {
  width: 100%;
  margin-top: -3.4rem;
}
.contenedor-home {
  /* padding-top: 100px; */
  background: #f5f5f5;
  padding-bottom: 3%;
}
.linea {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: auto;
  margin-top: 7vh;
  margin-bottom: 7vh;
}

.linea h5 {
  font-weight: 600;
  color: #4b4a49;
  font-size: 16px;
}

.izquierdo {
  width: 33vw;
  height: 1px;
  background: #4b4a49;
  margin-bottom: 1%;
}

.derecho {
  height: 1px;
  width: 33vw;
  background: #4b4a49;
  margin-bottom: 1%;
}
.carouselNoticias {
  /* height: 60vh; */
  /* background-color: rebeccapurple; */
  align-items: center;
  /* padding-bottom: 5%; */
}
@media (max-width: 500px) {
  .carouselNoticias {
    /* height: auto; */
    /* position: relative; */
    margin-top: 5%;
  }
  .contenedor-home {
    width: 100%;
    height: 100%;
    /* padding-bottom: 1rem; */
    /* width: 40vw; */
  }
  .linea {
    text-align: center;
    margin-top: 3%;
    margin-bottom: 3%;
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
  .masGestiones {
    border-radius: 40px;
    background: linear-gradient(
      91deg,
      #00c3a8 -19.31%,
      #ffb900 74.46%,
      #ff2745 160.28%
    );
    max-height: 29px;
    width: 50%;
    margin: auto;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-self: center;
    padding-top: 1.5%;
    margin-top: 5%;
    text-align: center;
  }
  .masGestiones p {
    font-size: 11px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
    color: #fff;
  }
}
</style>
