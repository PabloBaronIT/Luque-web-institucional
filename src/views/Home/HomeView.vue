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
    <ImagenComponent />
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
import TarjetasComponent from "@/components/Buscador/TarjetasComponent.vue";
import ImagenComponent from "@/components/Imagen/ImagenComponent.vue";
import CardEcoComponent from "@/components/Ecologico/CardEcoComponent.vue";
import GridProgramasComponent from "@/components/Programas/GridProgramasComponent.vue";
import CarouselComponent from "@/components/Carousel/CarouselComponent.vue";

export default {
  name: "HomeView",
  components: {
    // HelloWorld,
    TarjetasComponent,
    ImagenComponent,
    CardEcoComponent,
    GridProgramasComponent,
    CarouselComponent,
  },
};
</script>
<style scoped>
video {
  width: 100%;
  margin-top: -3.5rem;
}
.contenedor-home {
  /* padding-top: 100px; */
  background: #f5f5f5;
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
  height: 60vh;
  /* background-color: rebeccapurple; */
  align-items: center;
}
</style>
