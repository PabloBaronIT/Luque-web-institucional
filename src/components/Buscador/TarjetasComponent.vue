<template>
  <div class="contenedor">
    <div class="top"><h6>Gestiones más consultadas</h6></div>
    <div class="buscador">
      <label for="">Buscar</label>
      <input type="text" name="" id="" />
      <div>
        <i class="bi bi-search" style="color: white; font-size: 20px"></i>
      </div>
    </div>
    <h1>Gestiones más consultadas</h1>
    <!-- MOBILE -->
    <div class="carousel-mobile">
      <carousel :items-to-show="3" :wrapAround="true" :transition="500">
        <slide
          v-for="slide in this.gestiones"
          :key="slide"
          @click="setClass()"
          :class="{ hovermobile: hover }"
        >
          <router-link to="/pueblo/historia" class="interior">
            <img :src="slide.imagen" alt="" />
            <h5>{{ slide.titulo }}</h5>
          </router-link>
        </slide>

        <template #addons>
          <!-- <navigation /> -->
        </template>
      </carousel>
    </div>
    <!-- WEB -->
    <div class="gridcontainer">
      <div
        v-for="(item, index) in gestiones"
        :key="index"
        class="cardGestiones"
      >
        <div class="card-body">
          <div><img :src="item.imagen" alt="" /></div>
          <div class="titulo">
            <h5>
              {{ item.titulo }}
            </h5>
          </div>
        </div>
      </div>
    </div>
    <div class="masGestiones">
      <p>Ingresá aquí para más gestiones</p>
    </div>
    <!-- <CaroulselTarjetasComponent /> -->
  </div>
</template>
<script>
import { Carousel, Slide } from "vue3-carousel";
export default {
  name: "TarjetasComponent",
  components: {
    Carousel,
    Slide,
    // Navigation,
  },
  data() {
    return {
      gestiones: [
        {
          titulo: "LICENCIA DE CONDUCIR",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206111/icon-licencia_tmokfa.png",
        },
        {
          titulo: "COMERCIO",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206172/icon-habilitaciones_azoanu.png",
        },
        {
          titulo: "ALUMBRADO PÚBLICO",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206221/icon-alumbrado_vw51wl.png",
        },
        {
          titulo: "CATASTRO Y OBRAS",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206267/Frame_6_lyox01.png",
        },
        {
          titulo: "REGISTRO CIVIL",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206318/icon-registro_duivid.png",
        },
        {
          titulo: "CALLES Y VEREDAS",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206364/icon-calles_yhfcha.png",
        },
        {
          titulo: "PROVEEDORES MUNICIPALES",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206405/icon-proveedores_jifoss.png",
        },
        {
          titulo: "PAGOS",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1706206476/icon-peso_lzme9t.png",
        },
      ],
      hover: false,
    };
  },
  methods: {
    setClass() {
      this.hover = true;
    },
  },
};
</script>
<style scoped>
.contenedor {
  position: relative;
  background: #fff;
  color: rgba(255, 255, 255, 0.432);
  /* height: 100%; */
  width: 86%;
  margin: auto;
  margin-top: 3%;
  padding-top: 2rem;
  background-image: url("./../../assets/images/Frame.svg");
  /* opacity: 0.2; */
  background-repeat: space;
  background-position: center;
  text-align: center;
  overflow: hidden;
  border-radius: 50px 0px;

  /* filter: blur(25px); */
}
h1 {
  color: #00c3a8;
  font-weight: 600;
  margin-top: 2rem;
  margin-bottom: 1rem;
  font-family: "Source Sans 3", sans-serif;
  font-size: 50px;
}
.top {
  position: absolute;
  top: 0;
  width: 100%;
  height: 8%;
  background: linear-gradient(
    90deg,
    #00c3a8 0.18%,
    #ffb900 52.79%,
    #ff2745 107.64%
  );
  text-align: center;
  /* padding: 2%; */
}
.top h6 {
  visibility: hidden;
}
.buscador {
  position: absolute;
  width: 30%;
  height: 8%;
  background: #00c3a8;
  top: 0;
  right: 0;
  border-bottom-left-radius: 50px;
  text-align: left;
  padding-left: 4rem;
  display: flex;
  flex-direction: row;
  align-items: center;
}
label {
  color: white;
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}
input {
  background: none;
  border-style: none;
  margin-left: 0.5rem;
  margin-right: 1rem;
  width: 60%;
}
.gridcontainer {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 25px;
  margin: auto;
  /* margin-top: 3%; */
  grid-auto-rows: minmax(110px, auto);
  width: 85%;
  margin-bottom: 3%;
}
h5 {
  color: #3e3e3e;
  font-size: 18px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  margin-left: 3%;
}
.cardGestiones {
  /* display: flex;
  flex-direction: row; */

  border-radius: 16px;
  background: #fff;
  padding: 0.2rem;
  /* padding-left: 3%; */
  box-shadow: 4px 4px 4px 0px rgba(0, 0, 0, 0.25);
  min-height: 102px;
  min-width: 236px;
  transition: background 0.8s ease-in-out;
}
.card-body {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  border-radius: 16px;
  height: 100%;
  width: 100%;
  text-align: left;
  background: white;
}
.card-body img {
  max-width: 44px;
  min-height: 30px;
}
.cardGestiones:hover {
  background: linear-gradient(
    90deg,
    #00c3a8 0.01%,
    #ffb900 54.81%,
    #ff2745 104.96%
  );
  /* width: 110%; */
  /* position: relative; */
}
.titulo {
  width: 60%;
  margin-left: -10%;
}
.masGestiones {
  border-radius: 40px;
  background: linear-gradient(
    91deg,
    #00c3a8 -19.31%,
    #ffb900 74.46%,
    #ff2745 160.28%
  );
  min-height: 54px;
  width: 30%;
  margin: auto;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding-top: 1%;
  margin-bottom: 3%;
}
.masGestiones p {
  font-size: 18px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  color: #fff;
}

.carousel-mobile {
  display: none;
}
@media (max-width: 500px) {
  .contenedor {
    background-image: url("./../../assets/images/FrameMobile.svg");
    padding-top: 0;
    /* background-repeat: space;
  background-position: center; */
  }
  .top {
    width: 100%;
    background: #00c3a8;
    height: 31px;
    padding-top: 2%;
  }
  .top h6 {
    visibility: visible;
    font-size: 14px;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    color: #fff;
  }
  .contenedor {
    padding-top: 0;
    width: 90%;
    height: 130px;
    border-radius: 15px 0px 0px 0px;
    /* padding-bottom: 3rem; */
    padding-bottom: 3rem;
    position: relative;
  }
  .contenedor h1 {
    font-size: 14px;
    visibility: hidden;
  }
  .buscador {
    display: none;
  }
  h5 {
    color: #4b4a49;
    font-weight: 700;
  }
  .carousel-mobile {
    display: block;
    width: 100%;
    height: auto;
    margin-top: -6%;
  }
  .gridcontainer {
    display: none;
  }
  .masGestiones {
    display: none;
  }
  .carousel {
    width: 100%;
    height: 100%;
    /* margin: auto; */
    /* padding-left: 3rem; */
    /* padding-right: 3rem; */
  }
  .carousel__slide {
    padding: 1% 1%;
    background: #fff;
    min-height: 61px;
    min-width: 146px;
    border-radius: 8px;
    box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
    margin: 0.5rem;
    /* width: 18 vw; */
    /* width: 10vw; */
  }
  .carousel__slide:hover {
    background: linear-gradient(180deg, #019939 4.26%, #ffcc03 126.04%);
  }
  .hovermobile {
    background: linear-gradient(180deg, #019939 4.26%, #ffcc03 126.04%);
  }
  .interior {
    height: 100%;
    width: 100%;
    background: #fff;
    border-radius: 8px;
    text-align: center;
    /* padding: 1.5rem 1.5rem; */
    text-decoration: none;
    text-align: center;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  .interior h5 {
    font-size: 11px;
  }
  .interior h5:hover {
    color: #019939;
  }
  .interior img {
    height: 34px;
    width: 34px;
  }
}
</style>
