<template>
  <nav class="top-nav-container">
    <router-link to="/"
      ><img src="@/assets/images/LogoLuque.svg" alt="" class="logo-muni"
    /></router-link>
    <i class="bi bi-list burguer" @click="this.setMenu"> </i>
    <div class="menu" v-if="this.menu">
      <div
        class="item-menu"
        @click="this.setSubMenu(index)"
        v-for="(item, index) in this.ListMenu"
        :key="index"
      >
        <h6>
          {{ item.titulo }}
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="10"
            height="10"
            viewBox="0 0 10 10"
            fill="none"
          >
            <path
              d="M2.1875 3.59375L5 6.40625L7.8125 3.59375"
              stroke="#3E3E3E"
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </h6>
        <div
          class="item-subMenu"
          v-if="this.open === true && this.itemSelect === index"
        >
          <h6 v-for="(item, index) in item.subtitulos" :key="index">
            {{ item }}
          </h6>
        </div>
        <div class="linea-menu"></div>
      </div>
    </div>
    <router-link to="/"
      ><img
        src="@/assets/images/LogoBlancoLuque.svg"
        alt=""
        class="logo-muni-mobile"
    /></router-link>

    <div class="contenedor">
      <input type="text" name="" id="" v-model="this.valor" />
      <i class="bi bi-search lupa"></i>
      <!-- <svg
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
      </svg> -->
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
      <!-- MOBILE -->
      <div class="redes-container-mobile">
        <a href="">
          <img class="redes" src="@/assets/images/Lupa.svg" alt="" />
        </a>
        <a href="">
          <img class="redes" src="@/assets/images/InstagramB.svg" alt="" />
        </a>
        <a href="">
          <img class="redes" src="@/assets/images/FacebookB.svg" alt="" />
        </a>
      </div>
      <div class="tiempo">
        <!-- <div class="sol"></div> -->
        <img :src="this.icono" alt="imagen" class="icono" />
        <h6 style="font-weight: 600">{{ temperatura }}</h6>
        <p style="margin-top: -0.5rem">{{ tiempo }}</p>
      </div>
    </div>
  </nav>
  <div class="botones" :class="{ fixed: isSticky }">
    <div class="dropdown">
      <button
        class="btn btn dropdown-toggle asd"
        :class="{ asd: isSticky }"
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
import axios from "axios";

export default {
  name: "topNavComponent",
  data() {
    return {
      valor: "",
      isSticky: false,
      temperatura: 0,
      tiempo: "",
      icono: "",
      menu: false,
      open: false,
      itemSelect: null,
      ListMenu: [
        {
          titulo: "EL PUEBLO",
          subtitulos: [
            "Nuestra Historia",
            "Luque Hoy",
            "Descubrí Luque",
            "Fiesta Nacional",
          ],
          open: false,
        },
        {
          titulo: "NUESTRO GOBIERNO",
          subtitulos: ["asd", "asdasd", "asdasdasdasd"],
          open: false,
        },
        {
          titulo: "SERVICIO AL VECINO",
          subtitulos: ["asd", "asdasd", "asdasdasdasd"],
          open: false,
        },
        {
          titulo: "NOVEDADES",
          subtitulos: ["asd", "asdasd", "asdasdasdasd"],
          open: false,
        },
      ],
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
    this.getTiempo();
  },
  methods: {
    handleScroll() {
      // Verifica la posición de desplazamiento para determinar si se activa el sticky
      this.isSticky = window.scrollY > 100; // Puedes ajustar el valor según tus necesidades
    },
    getTiempo() {
      axios
        .get(
          "https://api.tutiempo.net/json/?lan=es&apid=a5GX44aXXaahzCV&ll=-31.6476686,-63.3444"
        )
        .then((response) => {
          console.log(response);
          this.temperatura = response.data.hour_hour.hour1.temperature;
          this.tiempo = response.data.hour_hour.hour1.text;
          let icon = response.data.hour_hour.hour1.icon;
          // let dia = new Date();
          // this.dia = dia.getDate();
          // this.getDia(dia.getDay());
          // this.getMes(dia.getMonth());
          // this.text = asd.split(" ");
          // this.text = this.text[0].toUpperCase();
          // this.text = asd.toUpperCase();

          this.icono = `https://v5i.tutiempo.net/wi/02/30/${icon}.png`;
        });
    },
    setMenu() {
      this.menu = !this.menu;
    },
    setSubMenu(index) {
      console.log("soy el indice");
      this.itemSelect = index;
      this.open = !this.open;
      // this.ListMenu[index].open = true;
    },
  },
};
</script>

<style scoped>
/* .bi {
  display: none;
} */
.burguer {
  display: none;
}
.logo-muni {
  width: 180px;
}
.logo-muni-mobile {
  visibility: hidden;
}
.asd {
  opacity: 1;
  z-index: 200;
  color: white;
}
.top-nav-container {
  height: 106px;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;
  padding-right: 1.5%;
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
  z-index: 5;
  /* position: -webkit-sticky; */
  /* bottom: -3.3rem; */
}
.fixed {
  position: fixed;
  z-index: 100;
  top: 0;
  width: 100%;
  /* max-width: 100%; */
  height: 55px;
  margin: auto;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-around;
  align-items: center;
  /* margin-left: 6.5rem; */
  border-radius: 0px 0px 0px 0px;
  background: linear-gradient(
    90deg,
    #00c3a8 0.01%,
    #ffb900 54.81%,
    #ff2745 104.96%
  );
  opacity: 0.6;
  color: #fff;
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
.redes-container-mobile {
  display: none;
}
.tiempo {
  width: 12%;
  background: white;
  height: 80px;
  display: block;
  /* flex-direction: column; */
  justify-content: center;
  text-align: center;
  border-radius: 8px;
  padding: 0.5rem 0;
}
.tiempo p {
  font-size: 10px;
}
.icono {
  height: 30px;
  width: 30px;
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
  width: 58%;
  height: 45%;
  border-radius: 16px;
  border: none;
  background: #fff;
}
.lupa {
  color: #ff2745;
  font-size: 27px;
  position: relative;
  margin-left: -5rem;
  /* margin-top: 1%; */
}
.menu {
  display: none;
}
@media (max-width: 500px) {
  .burguer {
    /* visibility: visible; */
    display: block;
    color: white;
    font-size: 30px;
  }
  .menu {
    display: block;
    position: absolute;
    top: 6%;
    width: 100%;
    height: auto;
    background: #fff;
    z-index: 15;
  }
  .menu h6 {
    color: #3e3e3e;
    font-size: 12px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
  }
  .item-menu {
    /* border-bottom: 1px solid #00c3a8; */
    /* border-bottom-color: linear-gradient(
      90deg,
      #00c3a8 0.01%,
      #ffb900 54.81%,
      #ff2745 104.96%
    ); */
    position: relative;
    display: flex;
    flex-direction: column;
    /* align-items: center; */
    height: auto;
    padding-left: 5%;
  }
  .linea-menu {
    height: 1px;
    background: linear-gradient(
      90deg,
      #00c3a8 0.01%,
      #ffb900 54.81%,
      #ff2745 104.96%
    );
    width: 95%;
    position: absolute;
    bottom: 0;
    left: 2%;
  }
  .item-subMenu {
    /* display: block; */
    position: relative;
    /* top: 6%; */
    padding-left: 5%;
    width: 100%;
    height: auto;
    background: #fff;
  }
  .top-nav-container {
    width: 100%;
    background: linear-gradient(
      90deg,
      #00c3a8 0.01%,
      #ffb900 54.81%,
      #ff2745 104.96%
    );
    height: 56px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  .botones {
    visibility: hidden;

    /* display: none; */
  }
  .logo-muni {
    width: 107px;
    height: 32px;
  }
  .tiempo,
  .lupa,
  input {
    display: none;
  }
  .redes-container-mobile {
    visibility: visible;
    width: 50%;
    display: flex;
    justify-content: space-between;
    /* background-color: #00c3a8; */
  }
  .redes-container {
    visibility: hidden;
  }
  .logo-muni {
    display: none;
  }
  .logo-muni-mobile {
    visibility: visible;
    width: 107px;
    margin-left: -1rem;
  }
}
@media (max-width: 1200px) {
}
</style>
