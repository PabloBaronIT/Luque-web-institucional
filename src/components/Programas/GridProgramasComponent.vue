<template>
  <div class="grid">
    <div>
      <router-link to="/ciudad" class="item item0">
        <!-- <img :src="item.imagen" alt="imagen" /> -->
        <img src="@/assets/images/Produccion.svg" alt="" />

        <div class="titulo">
          <h3>PRODUCCIÓN</h3>
        </div>
      </router-link>
    </div>
    <div>
      <router-link to="/ciudad" class="item item1">
        <!-- <img :src="item.imagen" alt="imagen" /> -->
        <img src="@/assets/images/Obras-Publicas.svg" alt="" />

        <div class="titulo">
          <h3>OBRAS PÚBLICAS</h3>
        </div>
      </router-link>
    </div>
    <div>
      <router-link to="/ciudad" class="item item2">
        <!-- <img :src="item.imagen" alt="imagen" /> -->
        <img src="@/assets/images/Ambiente.svg" alt="" />

        <div class="titulo">
          <h3>AMBIENTE</h3>
        </div>
      </router-link>
    </div>
    <div>
      <router-link to="/ciudad" class="item item3">
        <!-- <img :src="item.imagen" alt="imagen" /> -->
        <img src="@/assets/images/Cultura.svg" alt="" />

        <div class="titulo">
          <h3>CULTURA</h3>
        </div>
      </router-link>
    </div>
    <div>
      <router-link to="/ciudad" class="item item4">
        <!-- <img :src="item.imagen" alt="imagen" /> -->
        <img src="@/assets/images/Educacion.svg" alt="" />

        <div class="titulo">
          <h3>EDUCACIÓN</h3>
        </div>
      </router-link>
    </div>
    <div>
      <router-link to="/ciudad" class="item item5">
        <!-- <img :src="item.imagen" alt="imagen" /> -->
        <img src="@/assets/images/Empleo.svg" alt="" />

        <div class="titulo">
          <h3>EMPLEO</h3>
        </div>
      </router-link>
    </div>
  </div>
  <div class="gridMobile">
    <Carousel :itemsToShow="1.2" :wrapAround="true" :transition="600">
      <Slide v-for="slide in this.datos" :key="slide">
        <img :src="slide.imagen" alt="imagen" />

        <div>
          <p style="margin-top: -0.5rem">{{ slide.titulo }}</p>
        </div>
        <!-- <p>Habilitacion de comercio</p> -->
      </Slide>
      <!-- <template #addons> -->
      <!-- <Navigation /> -->
      <!-- <Pagination /> -->
      <!-- </template> -->
    </Carousel>
  </div>
</template>
<script>
import { Carousel, Slide } from "vue3-carousel";

export default {
  name: "GridProgramasComponent",
  data() {
    return {
      datos: [
        {
          titulo: "PRODUCCION",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706293915/Frame_ljki0p.png",
        },
        {
          titulo: "OBRAS PUBLICAS",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706293915/Frame_ljki0p.png",
        },
        {
          titulo: "AMBIENTE",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706293915/Frame_ljki0p.png",
        },
        {
          titulo: "CULTURA",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706293915/Frame_ljki0p.png",
        },
        {
          titulo: "EDUCACION",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706293915/Frame_ljki0p.png",
        },
        {
          titulo: "EMPLEO",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706293915/Frame_ljki0p.png",
        },
      ],
    };
  },
  components: {
    Carousel,
    Slide,
    // Pagination,
    // Navigation,
  },
};
</script>
<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* Crea 3 columnas de igual tamaño */
  grid-template-rows: repeat(2, 1fr); /* Crea 3 filas de altura fija de 100px */
  gap: 25px;
  margin: auto;
  /* margin-bottom: 10vh; */
  width: 80%;
  /* background: rebeccapurple; */
  /* background: linear-gradient(
      90deg,
      #019939 -3.32%,
      #ffcc03 49.27%,
      #e52320 110.14%
    ); */
  /* grid-auto-rows: minmax(100px, auto); */
}
.gridMobile {
  visibility: hidden;
}
img {
  max-width: 50%;
  max-height: 70%;
}
h3 {
  font-weight: 900;
  font-size: 24px;
  font-style: normal;
  letter-spacing: 1.5px;
}
.titulo {
  width: 57%;
}
.item {
  border-radius: 20px;
  margin: auto;
  width: 345px;
  height: 148px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
  color: white;
  padding-left: 1rem;
}
a {
  text-decoration: none;
}
.item0,
.item3 {
  background: linear-gradient(106deg, #00c3a8 0%, #ffb900 101.17%);
}
.item1,
.item4 {
  background: linear-gradient(
    91deg,
    #00c3a8 -63.1%,
    #ffb900 56.31%,
    #ff2745 165.6%
  );
}
.item2,
.item5 {
  background: linear-gradient(92deg, #ffb900 1.51%, #ff2745 109.53%);
}

@media (max-width: 500px) {
  .grid {
    display: none;
    width: 100%;
  }
  .contenedor {
    /* width: 100%; */
    /* height: 121px; */
    /* margin: auto; */
    /* margin-bottom: 10%; */
    /* padding: 0 0; */
    /* padding: 0 2rem; */
    background: red;
  }
  .gridMobile {
    visibility: visible;
    width: 100%;
    height: 100%;
    margin: auto;
    /* margin-top: -20rem; */

    /* margin-bottom: 10%; */
    /* padding: 0 0; */
    padding: 0 2rem;
    /* background: red; */
  }
  .carousel {
    width: 100%;
    height: 130px;
    /* margin: auto; */
    /* padding: 1rem; */
    /* background: rebeccapurple; */
    /* padding-left: 3rem; */
    /* padding-right: 3rem; */
  }
  .carousel__slide {
    padding: 0.3rem 0.3rem;
    background: #fff;
    height: 115px;
    max-width: 90%;
    border-radius: 12px;
    box-shadow: 8px 5px 10px 0px rgba(0, 0, 0, 0.2);
    margin: 0.5rem;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    background: linear-gradient(
      102deg,
      #00c3a8 0.57%,
      #ffb900 63.91%,
      #ff2745 121.88%
    );
    align-items: center;
    /* width: 18 vw; */
    /* width: 10vw; */
  }
  .carousel__slide p {
    font-size: 16px;
    color: white;
    font-weight: 600;
  }
  .carousel__slide:hover {
    background: linear-gradient(180deg, #019939 4.26%, #ffcc03 126.04%);
  }
  .interior {
    height: 100%;
    width: 100%;
    background: #fff;
    border-radius: 17px;
    text-align: center;
    padding: 1.5rem 1.5rem;
    text-decoration: none;
    text-align: center;
  }
  .interior h5:hover {
    color: #019939;
  }
}
</style>
