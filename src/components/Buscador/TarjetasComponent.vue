<template>
  <div class="contenedor">
    <div class="top"></div>
    <div class="buscador">
      <label for="">Buscar</label>
      <input type="text" name="" id="" />
      <div>
        <i class="bi bi-search" style="color: white; font-size: 20px"></i>
      </div>
    </div>
    <h1>Gestiones más consultadas</h1>
    <div class="gridcontainer">
      <div
        v-for="(item, index) in gestiones"
        :key="index"
        class="cardGestiones"
      >
        <div class="card-body">
          <div><img :src="item.imagen" alt="" /></div>
          <h5>
            {{ item.titulo }}
          </h5>
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
// import CaroulselTarjetasComponent from "@/components/Carousel/CarouselTarjetasComponent.vue";
export default {
  name: "TarjetasComponent",
  components: {
    // CaroulselTarjetasComponent,
  },
  data() {
    return {
      gestiones: [
        {
          titulo: "LICENCIA DE CONDUCIR",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1703006870/icon-licencia_oelvrg.svg",
        },
        {
          titulo: "COMERCIO",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1693345628/Group_10_cozjdd.svg",
        },
        {
          titulo: "ALUMBRADO PÚBLICO",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1693345591/Group_9_a5nlfm.svg",
        },
        {
          titulo: "CATASTRO Y OBRAS",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1693256926/Group_j2cw4e.svg",
        },
        {
          titulo: "REGISTRO CIVIL",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1701805280/icon-registro_eoepes.svg",
        },
        {
          titulo: "CALLES Y VEREDAS",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1693341288/Group_6_x0z8lh.svg",
        },
        {
          titulo: "PROVEEDORES MUNICIPALES",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1693257709/Group_4_l3ked2.svg",
        },
        {
          titulo: "PAGOS",
          imagen:
            "https://res.cloudinary.com/ddko88otf/image/upload/v1693256771/Vector_cfrwyo.svg",
        },
      ],
    };
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
  background-image: url("./../../assets/images/LetraL.svg");
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
  /* font-size: 50px; */
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
  margin-top: 3%;
  grid-auto-rows: minmax(110px, auto);
  width: 85%;
  margin-bottom: 3%;
}
h5 {
  color: #3e3e3e;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  margin-left: 3%;
}
.cardGestiones {
  display: flex;
  flex-direction: row;

  border-radius: 16px;
  background: #fff;
  padding: 0.2rem;

  box-shadow: 4px 4px 4px 0px rgba(0, 0, 0, 0.25);
  height: 100%;
}
.card-body {
  background: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  border-radius: 16px;
  height: 100%;
  width: 100%;
  padding: 0 5%;
  /* max-height: 80px; */

  /* width: 100%; */
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
</style>
