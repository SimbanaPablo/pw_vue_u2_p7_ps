<template>
    <div class="container">
 
  <img :src="imagen" alt="No se puede ver la IMG" width="550px" height="350px">
        <div class="seccion-pregunta">
 
       
    <input v-model="pregunta" type="text" placeholder="Any Question?">
    <p>Al final de la pregunta termina con una interrogación</p>
    <h1>{{ pregunta }}</h1>
    <h2>{{ respuesta }}</h2>
</div>
</div>
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

<style>
p, h1{
    color: white;
}
h2{
    background: white;
    color: black;
}
img{
    max-height: 100%;
    height: 100vh;
    max-width: 100%;
    width: 100vw;
    position: fixed;
    top: 0px;
    left:0px;
}
.seccion-pregunta{
    position: relative;
}
input {
margin-top: 35%;
width: 260px;
padding: 15px 30px;
border: none;
border-radius: 7px;
font-size: 18px;
}
</style>