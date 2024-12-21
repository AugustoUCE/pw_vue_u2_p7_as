<template>
    <img :src="imagen" alt="No se puede ver">
    <input v-model="pregunta" type="text" placeholder="Hazme una pregunta">
    <p>Recuerda que cuando finalices tu pregunta dar un ?</p>
    <h1>{{ pregunta }}</h1>
    <h2>{{ respuesta }}</h2>
</template>

<script>
export default {
  data() {
    return {
      pregunta: 'Hola mundo',
      respuesta: null,
      imagen: 'https://yesno.wtf/assets/yes/1-af11222d8d4af90bdab8fc447c8cfebf.gif"'
    };
  },
  watch: {
    //como pongo el observador declaro como unobj
    //value es el nuevo valor, oldValue es el valor anterior
    pregunta(value, oldValue) {
      console.log(value);
      console.log(oldValue);
      if (value.includes('?')) {
        //programar la llamada al API para obtener el SI o NO, y la img
        console.log('Llamar al API');
        this.llamarAPI();
      }
    }
  },
  methods: {
    //metodo para llamar al API
    async llamarAPI() {
      //siempre que llamemos a un API se debe hacer con async y await
      const data = await fetch('https://yesno.wtf/api').then(respuesta => respuesta.json());
      this.respuesta = data.answer;
      this.imagen = data.image;
      console.log(data);

    },
    async fachada(){
        await this.llamarAPI();
    }
  },

};
</script>
<style scoped>

</style>