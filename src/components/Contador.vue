<template>
    <h2>{{ encabezado }} : {{ valor2 }}</h2>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <div>
        <button @:click="incrementar()">+ 1</button>
        <button v-on:click="decrementar()">- 1</button>
    </div>
    <div v-if="esVerdad">
        <h1>Feliz Navidad</h1>
    </div>

</template>

<script>
export default {
    data() {
        return {
            numero: this.valor,
            titulo: 'Contador'
        }
    },
    methods: {
        calcularCuadrado() {
            console.log("entro al metodo");
            return this.numero * this.numero;
        },
        incrementar() {
            this.numero++;
        },
        decrementar() {
            this.numero--;
        }

    },
    computed: {
        calcularCuadradoComputado() {
            console.log("entro al metodo computado");
            return this.numero * this.numero;
        }
    },
    //primera forma de declaracion de un props
    //props:['encabezado','valor']
    props:{
        //encabezado: String,
        encabezado:{
            type:String,
            validator(value){
                if(value.includes === 'H'){
                    
                }else{
                    return value;
                } 
            }

        },
        valor: Number,
        valor2:{
            type:Number,
            required:false,
            default:77,
            validator(value){
                //Programo mi validacion bajo mi criterio y retorno true
                //cuando es valido para mi
                //retorno false cuando no es valido para mi
                return value <=77  //retorna true cada vez que cumpla la condicion
            }
        },
        esVerdad:{
            type: Boolean,
            required: true
        },  
        arreglo:Array,
        fecha:Date,
        ObjetoPersona:Object,
    }
}
</script>

<style>
button {
    background: #64B687;
    border-radius: 25px;
    border: solid 1px white;
    color: white;
    cursor: pointer;
    margin: 0px 5px;
    padding: 5px 15px;
}

button:hover {
    background: #5aa67b;
}
</style>