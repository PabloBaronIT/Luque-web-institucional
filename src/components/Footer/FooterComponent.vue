<template>
  <footer>
    <div class="telefonos-container">
      <div>
        <img
          src="./../../assets/images/LogoBlancoLuque.svg"
          alt="logo"
          class="logo"
        />
      </div>
      <div class="telefonos">
        <div class="telefono">
          <h6>CENTRO DE SALUD</h6>
          <div style="display: flex; align-items: center">
            <i class="bi bi-telephone-fill asd"></i>
            <h1>107</h1>
          </div>
        </div>

        <div class="linea"></div>
        <div class="telefono">
          <h6>POLICÍA</h6>
          <div style="display: flex; align-items: center">
            <i class="bi bi-telephone-fill asd"></i>
            <h1>101</h1>
          </div>
        </div>
        <div class="linea"></div>
        <div class="telefono">
          <h6>BOMBEROS</h6>
          <div style="display: flex; align-items: center">
            <i class="bi bi-telephone-fill asd"></i>
            <h1>100</h1>
          </div>
        </div>
      </div>

      <div class="foterMobile">
        <img src="./../../assets/images/LogoBlancoLuque.svg" alt="logo" />
        <div class="linea" style="height: 22px"></div>

        <div class="direccionMobile">
          <h5>
            Municipalidad de Luque 9 de julio 806, Luque, Córdoba CP X5967 TEL.:
            03573 48-0113
          </h5>
        </div>
      </div>
    </div>
    <h5 class="direccion">
      Municipalidad de Luque | 9 de julio 806, Luque, Córdoba | CP X5967 | TEL.:
      03573 48-0113
    </h5>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
};
</script>

<style scoped>
footer {
  /* margin: 0; */
  background: linear-gradient(
    90deg,
    #00c3a8 0.01%,
    #ffb900 54.81%,
    #ff2745 104.96%
  );
  /* background: var(--blue); */
  display: flex;
  flex-flow: column wrap;
  height: 40%;
  /* box-shadow: 0px 0px 15px #aaa; */
  align-items: center;
  justify-content: center;
  padding: 2%;
  width: 100%;
}
h1 {
  font-size: 64px;
  font-style: normal;
  font-weight: 800;
  line-height: normal;
}
.asd {
  font-size: 38px;
}
.linea {
  height: 130px;
  width: 1px;
  background: white;
}
/* h4 {
  font-weight: 400;
  line-height: normal;
} */
.telefonos-container {
  width: 88%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  /* background: rgba(245, 245, 245, 0.15); */
  /* backdrop-filter: blur(7.5px); */
  /* border-radius: 50px 0px; */
  /* padding-top: 1rem; */
  margin-bottom: 2%;
}
.telefonos {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  width: 45%;
  color: white;
  height: auto;
  align-items: center;
  /* margin-top: 1vh; */
  /* margin-bottom: -1rem; */
}
.telefono {
  text-align: center;
}
.telefono h6 {
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  margin-bottom: -1%;
}
.logo {
  width: 392px;
  height: 116px;
}

.direccion {
  color: white;
  font-weight: 300;
  line-height: normal;
  letter-spacing: 1px;
}
.foterMobile {
  display: none;
}
@media (max-width: 500px) {
  footer {
    height: 161px;
    /* margin-top: 5%; */
    /* display: flex; */
    /* flex-direction: column; */
  }
  .telefonos-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 165px;
    width: 100%;
    margin-top: -2rem;
  }
  .telefonos {
    height: 30%;
    width: 75%;
    margin: auto;
  }
  .telefono {
    width: 80px;
    position: relative;

    text-align: center;
  }
  .telefono h6 {
    font-size: 10px;
    font-weight: 400;
    position: absolute;
    left: 10%;
    top: 75%;
  }
  h1 {
    font-size: 26px;
    /* margin-left: 5%; */
  }
  .asd {
    font-size: 16px;
  }
  .logo {
    display: none;
  }
  .foterMobile {
    visibility: visible;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding-left: 1rem;
  }
  .foterMobile img {
    width: 50%;
  }
  .direccionMobile {
    width: 42%;
    color: white;
    margin-bottom: -2%;
  }
  .direccionMobile h5 {
    font-size: 10px;
    font-style: normal;
    font-weight: 300;
    line-height: normal;
  }
  .direccion {
    display: none;
  }
  .linea {
    height: 60px;
  }
}
</style>
