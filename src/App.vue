<template>
  <NavTopComponent />
  <router-view />
  <FooterComponent />
</template>
<script>
import NavTopComponent from "./components/Nav/NavTopComponent.vue";
import FooterComponent from "./components/Footer/FooterComponent.vue";

export default {
  components: {
    NavTopComponent,
    FooterComponent,
  },
};
</script>
<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #ffffff;

  width: 100vw;
  /* text-align: center; */
  /* color: #2c3e50; */
}

@media (max-width: 500px) {
  #app {
    width: 100vw;
    height: auto;
    font-family: "Montserrat", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background: #ffffff;
  }
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
}
/* nav {
  padding: 30px;
} */

/* nav a {
  font-weight: bold;
  color: #2c3e50;
} */

/* nav a.router-link-exact-active {
  color: #42b983;
} */
</style>
