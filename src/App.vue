<template>
  
    <JuegoPage v-show="false" />


</template>

<script>
//para llamar a un componente se debe importar
import JuegoPage from "./pages/JuegoPage.vue";
export default {
  name: "App",
  components: {
    JuegoPage,
  },
 
};
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
