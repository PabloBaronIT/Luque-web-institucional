<template>
  <nav class="top-nav-container">
    <router-link to="/"
      ><img src="@/assets/images/LogoLuque.svg" alt="" class="logo-muni"
    /></router-link>
    <div class="contenedor">
      <input type="text" name="" id="" v-model="this.valor" />
      <!-- <i class="bi bi-search lupa"></i> -->
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="31"
        height="31"
        viewBox="0 0 31 31"
        fill="none"
        class="lupa"
      >
        <path
          d="M27.6512 25.5138L21.9543 19.817C23.3258 17.9911 24.0662 15.7686 24.0638 13.485C24.0638 7.65191 19.3181 2.90625 13.485 2.90625C7.65191 2.90625 2.90625 7.65191 2.90625 13.485C2.90625 19.3181 7.65191 24.0638 13.485 24.0638C15.7686 24.0662 17.9911 23.3258 19.817 21.9543L25.5138 27.6512C25.8022 27.9089 26.1783 28.0465 26.565 28.0357C26.9516 28.0249 27.3195 27.8665 27.593 27.593C27.8665 27.3195 28.0249 26.9516 28.0357 26.565C28.0465 26.1783 27.9089 25.8022 27.6512 25.5138ZM5.92875 13.485C5.92875 11.9905 6.37192 10.5296 7.20221 9.28697C8.0325 8.04435 9.21262 7.07585 10.5933 6.50394C11.9741 5.93202 13.4934 5.78238 14.9592 6.07394C16.4249 6.3655 17.7713 7.08516 18.8281 8.14192C19.8848 9.19869 20.6045 10.5451 20.8961 12.0108C21.1876 13.4766 21.038 14.9959 20.4661 16.3767C19.8942 17.7574 18.9256 18.9375 17.683 19.7678C16.4404 20.5981 14.9795 21.0413 13.485 21.0413C11.4817 21.0388 9.56113 20.242 8.14458 18.8254C6.72803 17.4089 5.93115 15.4883 5.92875 13.485Z"
          fill="url(#paint0_linear_8_242)"
        />
        <defs>
          <linearGradient
            id="paint0_linear_8_242"
            x1="27.7708"
            y1="2.58333"
            x2="-4.52083"
            y2="27.7708"
            gradientUnits="userSpaceOnUse"
          >
            <stop stop-color="#FF2745" />
            <stop offset="1" stop-color="#FFB900" />
          </linearGradient>
        </defs>
      </svg>
      <div class="redes-container">
        <a href="">
          <img class="redes" src="@/assets/images/Email.svg" alt="" />
        </a>
        <a href="">
          <img class="redes" src="@/assets/images/Instagram.svg" alt="" />
        </a>
        <a href="">
          <img class="redes" src="@/assets/images/Facebook.svg" alt="" />
        </a>
      </div>
      <div class="tiempo">
        <div class="sol"></div>
        <p style="font-weight: 600">26°</p>
        <p style="margin-top: -1.5rem">soleado</p>
      </div>
    </div>
  </nav>
  <div class="botones" :class="{ fixed: isSticky }">
    <div class="dropdown">
      <button
        class="btn btn dropdown-toggle"
        type="button"
        data-bs-toggle="dropdown"
        aria-expanded="false"
      >
        EL PUEBLO
      </button>
      <ul class="dropdown-menu">
        <li>
          <router-link to="/pueblo/historia" class="link">
            <a class="dropdown-item hoverMenu" href="#">Nuestra historia</a>
          </router-link>
        </li>

        <li>
          <router-link to="/pueblo/sacanta-hoy" class="link">
            <a class="dropdown-item hoverMenu" href="#">Sacanta hoy</a>
          </router-link>
        </li>
        <li>
          <router-link to="/pueblo/descubri-sacanta" class="link">
            <a class="dropdown-item hoverMenu" href="#">Descubrí Sacanta</a>
          </router-link>
        </li>
        <li>
          <router-link to="/pueblo/fiesta-nacional" class="link">
            <a class="dropdown-item hoverMenu" href="#">Fiesta Nacional</a>
          </router-link>
        </li>
      </ul>
    </div>
    <div class="dropdown">
      <button
        class="btn btn dropdown-toggle"
        type="button"
        data-bs-toggle="dropdown"
        aria-expanded="false"
      >
        NUESTRO GOBIERNO
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item hoverMenu" href="#">Action</a></li>
        <li>
          <a class="dropdown-item hoverMenu" href="#">Another action</a>
        </li>
        <li>
          <a class="dropdown-item hoverMenu" href="#">Something else here</a>
        </li>
      </ul>
    </div>
    <div class="dropdown">
      <button
        class="btn btn dropdown-toggle asd"
        type="button"
        data-bs-toggle="dropdown"
        aria-expanded="false"
      >
        SERVICIO AL VECINO
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item hoverMenu" href="#">Action</a></li>
        <li>
          <a class="dropdown-item hoverMenu" href="#">Another action</a>
        </li>
        <li>
          <a class="dropdown-item hoverMenu" href="#">Something else here</a>
        </li>
      </ul>
    </div>
    <div class="dropdown">
      <button
        class="btn btn dropdown-toggle"
        type="button"
        data-bs-toggle="dropdown"
        aria-expanded="false"
      >
        NOVEDADES
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item hoverMenu" href="#">Action</a></li>
        <li>
          <a class="dropdown-item hoverMenu" href="#">Another action</a>
        </li>
        <li>
          <a class="dropdown-item hoverMenu" href="#">Something else here</a>
        </li>
      </ul>
    </div>
  </div>
  <!-- <div class="colores">
    <div class="red"></div>
    <div class="green"></div>
    <div class="red"></div>
    <div class="green"></div>
    <div class="red"></div>
  </div> -->
</template>
<script>
export default {
  name: "topNavComponent",
  data() {
    return {
      valor: "",
      isSticky: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      // Verifica la posición de desplazamiento para determinar si se activa el sticky
      this.isSticky = window.scrollY > 100; // Puedes ajustar el valor según tus necesidades
    },
  },
};
</script>

<style>
.logo-muni {
  width: 180px;
}
</style>
<style scoped>
.top-nav-container {
  height: 106px;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;
  padding: 0% 1.5%;
  background: #f5f5f5;
  /* position: fixed; */
  /* z-index: 15; */
  width: 100%;
  /* padding: 1rem 1rem; */
}
.botones {
  width: 85%;
  /* height: 60%; */
  height: 55px;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-around;
  align-items: center;
  /* margin-left: 4.5rem; */
  margin: auto;
  border-radius: 0px 0px 16px 16px;
  background: var(
    --Degrad-completo,
    linear-gradient(90deg, #00c3a8 0.01%, #ffb900 54.81%, #ff2745 104.96%)
  );
  box-shadow: 1px -4px 4px 1px rgba(0, 0, 0, 0.15) inset;
  position: relative;
  /* position: -webkit-sticky; */
  /* bottom: -3.3rem; */
}
.fixed {
  position: fixed;
  z-index: 500;
  top: 0;
  /* width: 85%; */
  /* max-width: 100%; */
  height: 55px;
  margin: auto;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-around;
  align-items: center;
  margin-left: 6.5rem;
  border-radius: 0px 0px 16px 16px;
  background: var(
    --Degrad-completo,
    linear-gradient(90deg, #00c3a8 0.01%, #ffb900 54.81%, #ff2745 104.96%)
  );
  box-shadow: 1px -4px 4px 1px rgba(0, 0, 0, 0.15) inset;
}
.btn {
  color: white;
  font-size: 16px;
  font-weight: 700;
}
.btn:hover {
  color: #4b4a49;
}
.redes {
  max-width: 40px;
}

.redes-container {
  display: flex;
  width: 20%;
  justify-content: space-between;
  /* margin-left: -2rem; */
}
.tiempo {
  width: 10%;
  background: white;
  height: 80px;
  display: block;
  /* flex-direction: column; */
  justify-content: center;
  text-align: center;
  border-radius: 8px;
  padding: 0.5rem 0;
}
.sol {
  width: 29px;
  height: 29px;
  margin: auto;
  border-radius: 50%;
  background: #ffb900;
}

.hoverMenu:hover {
  color: #019939;
}
.link {
  text-decoration: none;
}
.contenedor {
  /* position: relative; */
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 45%;
  height: 100%;
}
input {
  width: 60%;
  height: 55%;
  border-radius: 16px;
  border: none;
  background: #fff;
}
.lupa {
  color: black;
  font-size: 27px;
  position: relative;
  margin-left: -5rem;
  /* margin-top: 1%; */
}
@media (max-width: 800px) {
  .contenedor {
    width: 40vw;
  }
}
@media (max-width: 1200px) {
  .contenedor {
    width: 50vw;
  }
}
</style>
