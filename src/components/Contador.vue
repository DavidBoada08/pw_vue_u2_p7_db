<template>
    <h2>{{titulo}}</h2>
    <p>{{numero}} <sup>{{exponente}}</sup>={{ calcularCuadradoComputado}}</p>
    <p>{{numero}} <sup>{{exponente}}</sup>={{ calcularCuadradoComputado}}</p>
    <p>{{numero}} <sup>{{exponente}}</sup>={{ calcularCuadradoComputado}}</p>
    <p>{{numero}} <sup>{{exponente}}</sup>={{ calcularCuadradoComputado}}</p>
    <p>{{numero}} <sup>{{exponente}}</sup>={{ calcularCuadradoComputado}}</p>
    <div>
        <button v-on:click="incrementar()">+1</button>
        <button v-on:click="decrementar">-1</button>
     
      
    </div>
  
</template>

<script>
export default {

    data() {
        return {
            numero: 10,
            exponente:2,
            titulo:'Contador'
        }
    },
    methods: {
        calcularCuadrado(){
            console.log('entro a calcular');
            return this.numero*this.numero;
        },
        incrementar(){
            this.numero++;
        },
        decrementar(){
            this.numero--;
        },
        aumentarExponente(){
            this.exponente++;
        }
    },
    computed: {
        calcularCuadradoComputado(){
            console.log('entro a calcular computado');
            return this.numero*this.numero;}
        
        }
    }
 


</script>

<style>
button{
    background-color: #4CAF50;
    border-radius: 5px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin: 0px 5px;
    padding: 5px 15px;
}
button:hover{
    background-color: #c7f3da;
}

</style>