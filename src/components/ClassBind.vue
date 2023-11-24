<template>
    <p :class="{ 'aviso': error }">El mensaje se ha enviado satisfactoriamente.</p>
    <p :style="{backgroundColor : '#ccc', color:c}">Hola Mundo</p>
    <button @click="cambioColor()" >Cambiar Color</button>
    <button @click="volverColor()" >Volver al anterior</button>
</template>

<!-- composition API -->

<!-- <script setup>
import { ref } from 'vue';
    let error = true
    let c = ref('#fff')
    const cambioColor = () => {c.value = '#ff0000'}
    const volverColor = () => {c.value = '#fff'}
</script> -->



<!-- option API -->
<script>
export default{
    name: 'ClassBind',
    data(){
        return{
            c:'#fff'
        }
    },
    methods:{
        cambioColor(){
            this.c = '#ff0000'
        },

        volverColor(){
            this.c = '#fff'
        }
    }
}
</script>

<style scoped>
.aviso {
    color: red;
}
</style>