<template>
    <h1>{{encabezado}} : {{ valor2 }}</h1>

    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado}}</p>
    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado}}</p>
    
    <div>
        <button @:click="incremetar()">+1</button>
        <button v-on:click="decrementar()">-1</button>

    </div>
    <div v-if="esVerdad">
        <h1>Feliz navidad</h1>

    </div>
    
   
    
</template>

<script>
export default {
    data(){
        return{
            numero: this.valor,
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
    },
    //se puede utilizar como propiedad reactiva
    //1 forma de declarar un props
   // props:['encabezado','valor']
    //2 forma
    props:{
        encabezado: {
            type: String,
            validator(value) {
            return typeof value === 'string' && value.trim().length > 0 && !value.includes('a');
            }
        },
        valor: Number,
        valor2:{
            type: Number,
            requeried:false,
            default:77, //este valor a salir cuando no requerido
            validator(value){
                //value es el valor que envia ES EL PROPS
                //programo mi vlaidacion bajo mi criterio y retorno true
                //cuando es valido para mi 
                //retorno false cuando no es valido para mi
                return value<=77;

            }
        },
        esVerdad: {
            type:Boolean,
            required:true
        },
        arreglo: Array,
        fecha: Date,
        objetoPersona: Object,

    },   
};

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