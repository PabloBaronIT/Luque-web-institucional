<template>
  <nav class="contenedor-nav">
    <router-link to="/"
      ><img src="@/assets/images/LogoLuque.svg" alt="" class="logo-muni"
    /></router-link>
    <div class="divburguer">
      <i class="bi bi-list burguer" @click="this.setMenu"> </i>
      <router-link to="/"
        ><img
          src="@/assets/images/LogoBlancoLuque.svg"
          alt=""
          class="logo-mobile"
      /></router-link>
    </div>

    <!-- MENU-BURGUER -->
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
          <router-link
            :to="item.link"
            class="link"
            @click="this.setMenu"
            v-for="(item, index) in item.subtitulos"
            :key="index"
          >
            <h6>
              {{ item.titulo }}
            </h6>
          </router-link>
        </div>
        <div class="linea-menu"></div>
      </div>
    </div>

    <div class="contenedor">
      <input type="text" name="" id="" v-model="this.valor" />
      <i class="bi bi-search lupa"></i>

      <div class="redes-container">
        <a href="">
          <img class="redes" src="@/assets/images/whats.svg" alt="" />
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
        <img :src="this.icono" alt="imagen" class="icono" />
        <h6 style="font-weight: 600">{{ temperatura }}°</h6>
        <p style="margin-top: -0.5rem">{{ tiempo }}</p>
      </div>
    </div>
  </nav>
  <div class="botones" :class="{ fixed: isSticky }">
    <div class="dropdown">
      <button
        class="btn btn dropdown-toggle asd"
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
            { titulo: "Nuestra Historia", link: "/pueblo/historia" },
            { titulo: "Luque Hoy", link: "/pueblo/luque-hoy" },

            { titulo: "Descubrí Luque", link: "/pueblo/descubri-luque" },

            { titulo: "Fiesta Nacional", link: "/pueblo/fiesta-nacional" },
          ],
        },
        {
          titulo: "NUESTRO GOBIERNO",
          subtitulos: [
            { titulo: "Nuestra Historia", link: "/pueblo/historia" },
            { titulo: "Luque Hoy", link: "/pueblo/luque-hoy" },

            { titulo: "Descubrí Luque", link: "/pueblo/descubri-luque" },

            { titulo: "Fiesta Nacional", link: "/pueblo/fiesta-nacional" },
          ],
        },
        {
          titulo: "SERVICIO AL VECINO",
          subtitulos: [
            { titulo: "Nuestra Historia", link: "/pueblo/historia" },
            { titulo: "Luque Hoy", link: "/pueblo/luque-hoy" },

            { titulo: "Descubrí Luque", link: "/pueblo/descubri-luque" },

            { titulo: "Fiesta Nacional", link: "/pueblo/fiesta-nacional" },
          ],
        },
        {
          titulo: "NOVEDADES",
          subtitulos: [
            { titulo: "Nuestra Historia", link: "/pueblo/historia" },
            { titulo: "Luque Hoy", link: "/pueblo/luque-hoy" },

            { titulo: "Descubrí Luque", link: "/pueblo/descubri-luque" },

            { titulo: "Fiesta Nacional", link: "/pueblo/fiesta-nacional" },
          ],
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
/* nav {
  width: 100%;
} */
.burguer {
  display: none;
}
.logo-muni {
  width: 180px;
}
.logo-mobile {
  /* visibility: hidden; */
  display: none;
}
/* .asd {
  opacity: 1;
  z-index: 200;
  color: white;
} */
.contenedor-nav {
  height: 106px;
  display: flex;
  flex-flow: row;
  justify-content: space-between;
  align-items: center;
  padding: 2%;
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
  z-index: 15;
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
    rgb(0, 195, 168, 0.6) 0.01%,
    rgb(255, 185, 0, 0.6) 54.81%,
    rgb(255, 39, 69, 0.6) 104.96%
  );
  color: #fff;
  box-shadow: 1px -4px 4px 1px rgba(0, 0, 0, 0.15) inset;
}
.btn {
  color: white;
  font-size: 16px;
  font-weight: 700;
  opacity: 1;
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
  max-height: 80px;
  display: block;
  /* flex-direction: column; */
  justify-content: center;
  text-align: center;
  border-radius: 8px;
  padding: 0.5rem 0;
  box-sizing: content-box;
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
  .divburguer {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 40%;
    margin-left: -32%;
    margin-top: 2%;
  }
  .burguer {
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
    left: 0;
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
    justify-content: center;
    height: auto;
    padding: 2% 2% 1%;
    align-self: center;
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
    padding: 0% 5%;
    width: 100%;
    height: auto;
    background: #fff;
  }
  .item-subMenu h6 {
    margin-bottom: 3%;
  }
  .contenedor-nav {
    /* position: fixed; */
    /* top: 0; */
    /* z-index: 165; */
    width: 100%;
    background: linear-gradient(
      90deg,
      #00c3a8 0.01%,
      #ffb900 54.81%,
      #ff2745 104.96%
    );
    height: 56px;
    /* display: flex; */
    /* flex-direction: row; */
    /* justify-content: space-between; */
  }
  .botones {
    visibility: hidden;
    /* display: none; */
  }
  .dropdown {
    display: none;
  }
  /* .logo-muni {
    width: 107px;
    height: 32px;
  } */
  .tiempo,
  .lupa,
  input {
    display: none;
  }
  .contenedor {
    width: 25%;
  }
  .redes-container-mobile {
    visibility: visible;
    width: 100%;
    display: flex;
    justify-content: space-around;
    /* background-color: #00c3a8; */
  }
  .redes-container {
    display: none;
  }
  .logo-muni {
    display: none;
  }
  .logo-mobile {
    /* visibility: visible; */
    display: block;
    width: 107px;
    /* margin-left: -60%; */
  }
}
@media (max-width: 1200px) {
}
</style>
