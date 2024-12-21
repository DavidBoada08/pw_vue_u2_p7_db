<template>
  <img :src="Imagen"
   alt="No se Puedes Ver">
   <br>
   <input v-model="pregunta" type="text" placeholder="Hazme una Pregunta">

   <p>Recuerda que cuando finalices tu pregunta dar un ?</p>

   <h1>{{pregunta}}</h1>

   <h2>{{respuesta}}</h2>
</template>

<script>
export default {
    data(){
        return{
            pregunta: 'Sigues ahi?',
            respuesta: null,
            Imagen: null
        }
    },
    watch:{
        pregunta(value, oldValue){
            console.log(value);
            console.log(oldValue);
            if(value.includes('?')){
                //programar la llamada al API
                // para obtener el si y el no, y la imagen
                console.log('Llamar a la API');
                this.llamarAPI();
            }
        }
    },
    methods:{
        async llamarAPI(){
            const data = await fetch('https://yesno.wtf/api')
            .then(resp => resp.json())
            this.respuesta = data.answer;
            this.Imagen = data.image;
            console.log(data);
            },
        },
    };

</script>

<style>

</style>