<template>
  <footer>
    <div class="telefonos-container">
      <div class="telefonos">
        <div class="telefono" name="primero">
          <div style="display: flex; align-items: center">
            <i class="bi bi-telephone-fill asd"></i>
            <h1>111</h1>
          </div>
          <h6>HOSPITAL</h6>
        </div>
        <div class="linea" name="primero"></div>
        <div class="telefono">
          <div style="display: flex; align-items: center">
            <i class="bi bi-telephone-fill asd"></i>
            <h1>147</h1>
          </div>
          <h6>
            ATENCIÓN AL <br />
            VECINO
          </h6>
        </div>
        <div class="linea"></div>
        <div class="telefono">
          <div style="display: flex; align-items: center">
            <i class="bi bi-telephone-fill asd"></i>
            <h1>101</h1>
          </div>
          <h6>POLICÍA</h6>
        </div>
        <div class="linea"></div>
        <div class="telefono">
          <div style="display: flex; align-items: center">
            <i class="bi bi-telephone-fill asd"></i>
            <h1>100</h1>
          </div>
          <h6>BOMBEROS</h6>
        </div>
      </div>
      <div class="logo">
        <img src="./../../assets/images/LogoBlancoLuque.svg" alt="logo" />
      </div>
      <div class="foterMobile">
        <img src="./../../assets/images/LogoBlancoLuque.svg" alt="logo" />
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
  height: 40vh;
  /* box-shadow: 0px 0px 15px #aaa; */
  align-items: center;
  justify-content: center;
  /* padding: 20px; */
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
  height: auto;
  width: 2px;
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
}
.telefonos {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  width: 60%;
  color: white;
  height: auto;
  /* margin-top: 1vh; */
  /* margin-bottom: -1rem; */
}
.telefono {
  text-align: center;
}
/* .numeros {
  color: #019939;
  font-size: 80px;
  font-weight: 900;
  line-height: normal;
  font-style: normal;
  margin-top: -5vh;
} */
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
    width: 80%;
    margin: auto;
  }
  .telefono h6 {
    font-size: 10px;
    font-weight: 400;
  }
  h1 {
    font-size: 26px;
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
  [name="primero"] {
    display: none;
  }
}
</style>
