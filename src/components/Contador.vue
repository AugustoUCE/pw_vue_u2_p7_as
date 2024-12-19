<template>
    <h1>{{titulo}}</h1>

    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado}}</p>
    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado}}</p>
    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado}}</p>
    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado}}</p>
    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado}}</p>
    <div>
        <button v-on:click="incremetar()">+1</button>
        <button v-on:click="decrementar()">-1</button>

    </div>
    
   
    
</template>

<script>
export default {
    data(){
        return{
            numero: 50,
            titulo: 'Contador'
        }
    },
    methods:{

        calcularCuadrado(){
            console.log('Entro calcularCuadrado Methods');
            return this.numero*this.numero;
        },
        incremetar(){
            this.numero++;
        },  
        decrementar(){
            this.numero --;
        },
    },
    computed:{
        //no se puede llamar las propiedad computadas por metodo 
        //se debe llamar como propiedad computada
        calcularCuadradoComputado(){
            console.log('Entro calcularCuadradoComputado');
            return this.numero*this.numero; 
        }
    }
    


}

</script>

<style>
button{
    background-color: #64B687;
    border-radius: 5px;
    color: white;
    border: 1px solid #eeeeee; 
    cursor: pointer;
    margin: 0px,5px ;
    padding: 10px 20px;

}
button:hover{
    background-color: #125c33;
}

</style>