<template>
    <h2>{{ titulo }}</h2>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ this.numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <div>
        <button v-on:click="incrementar()">+ 1</button>
        <button v-on:click="decrementar()">- 1</button>
    </div>

</template>

<script>
export default {
    data() {
        return {
            numero: 20,
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