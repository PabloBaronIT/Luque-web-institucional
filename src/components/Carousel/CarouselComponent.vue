<template>
  <Carousel
    :itemsToShow="3.2"
    :wrapAround="true"
    :transition="600"
    class="contenedor"
  >
    <Slide v-for="slide in this.novedades" :key="slide">
      <img :src="slide.imagen" alt="imagen" />

      <div class="interior-titulo" style="text-align: left">
        <router-link to="/historia">
          <p class="fecha">
            {{ new Date().toLocaleDateString() }}
          </p>
          <p style="margin-top: -0.5rem">{{ slide.titulo }}</p>
        </router-link>
      </div>
      <!-- <p>Habilitacion de comercio</p> -->
    </Slide>
    <template #addons>
      <Navigation />
      <!-- <Pagination /> -->
    </template>
  </Carousel>
</template>

<script>
import { Carousel, Slide, Navigation } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";

export default {
  name: "CarouselComponent",
  components: {
    Carousel,
    Slide,
    // Pagination,
    Navigation,
  },
  data() {
    return {
      novedades: [
        {
          titulo: "Reunión con el Pte. de la Agencia Córdoba Turismo.",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1683665000/sxli9cotqczr89ot2frw.png",
        },
        {
          titulo: "50° Fiesta Nacional de la Familia Piamontesa",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1689024361/bymphlvsesa0vr7t9msk.jpg",
        },
        {
          titulo: "Entrega de presente de primer niño nacido en 2024.",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1683665000/sxli9cotqczr89ot2frw.png",
        },
        {
          titulo: "Reunión con el Pte. de la Agencia Córdoba Turismo. ",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1689024361/bymphlvsesa0vr7t9msk.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.contenedor {
  width: 70%;
  height: 100%;
  margin: auto;
  /* margin-bottom: 10%; */
  /* padding: 0 0; */
  padding: 0 2rem;
  /* background: red; */
}
.carousel__slide {
  padding: 0 1%;
  background: #fff;
  height: 363px;
  border-radius: 16px;
  box-shadow: 8px 5px 10px 0px rgba(0, 0, 0, 0.2);
  display: flex;
  flex-direction: column;
  text-align: left;
  margin: auto;
  /* padding-left: 1rem; */

  /* width: 18 vw; */
  /* width: 10vw; */
}
a {
  color: #4b4a49;
  text-decoration: none;
}
a:hover {
  color: #333232;
}
img {
  height: 66%;
  width: 100%;
  border-radius: 16px;
}
.carousel__viewport {
  perspective: 2000px;
}

.carousel__track {
  transform-style: preserve-3d;
}

.carousel__slide--sliding {
  transition: 0.5s;
}

.carousel__slide {
  opacity: 0.5;
  transform: rotateY(-20deg) scale(0.9);
}

.carousel__slide--active ~ .carousel__slide {
  transform: rotateY(20deg) scale(0.9);
}

.carousel__slide--prev {
  opacity: 1;
  transform: rotateY(-30deg) scale(0.95);
  height: 363px;

  /* padding-top: 1rem; */
}

.carousel__slide--next {
  opacity: 1;
  transform: rotateY(10deg) scale(0.95);
  height: 363px;

  /* padding-top: 1rem; */
}

.carousel__slide--active {
  opacity: 1;
  transform: rotateY(0) scale(1.1);
  height: 363px;
  margin: 1.5rem 2rem;
}
.interior-titulo {
  width: 100%;
  /* margin: auto; */
  text-align: left;
  padding-left: 1rem;
  margin-top: 0.5rem;
}
.fecha {
  font-size: 13px;
  font-weight: 700;
}
@media (max-width: 500px) {
  .contenedor {
    height: 195px;
    width: 100%;
  }
  .slide {
    height: 100%;
    width: 100%;
    display: block;
  }

  .carousel__slide {
    height: 142px;
    padding: 0;
    border-radius: 16px;
    /* padding: 0 0.5rem; */
  }
  .carousel__slide--active {
    height: 142px;
    margin: 1.5rem 2.5rem;
    padding-top: 3px;
  }

  .interior-titulo p {
    font-size: 8px;
  }
  .interior-titulo {
    padding-left: 0.5rem;
  }
  img {
    height: 45%;
    width: 95%;
    border-radius: 16px;
  }
}
</style>
