<template>
    <img src="imagen" alt="no se puede ver">
    <input v-model="pregunta" type="text" placeholder="Hasme una pregunta">
    <p>Recuerda que cuando finalices tu pregunta, dar un ?</p>
    <h1>{{ pregunta }}</h1>
    <h2>{{ respuesta }}</h2>
</template>

<script>
export default {
    data() {
        return {
            pregunta: 'Quieres ser millonario?',
            respuesta:null,
            imagen:'https://yesno.wtf/assets/yes/14-b57c6dc03aa15a4b18f53eb50d6197ee.gif'
        };
    },
    watch: {
        pregunta(value, oldValue) {
            console.log(value);
            console.log(oldValue);
            if (value.includes('?')) {
                //Programar la llamda al API
                //Para obtener el SI o el NO, y la imagen
                console.log('Aqui llamo al API');
                this.llamarAPI()
            }
        }


    },
    methods: {
        async llamarAPI() {
            const data = await fetch("https://yesno.wtf/api").then(resp => resp.json());
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

<style></style>