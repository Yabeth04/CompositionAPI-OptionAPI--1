<template>
    <ul>
        <li v-for="(lista, index) in listaPaises" :key="index.norte"> {{ index }} {{ lista.centro }}</li>
    </ul>
</template>

<script setup>
import { ref } from 'vue'

// let listaPaises = ref(['Costa Rica','nicaragua','Islas Marshall'])  
let listaPaises = ref([
    {
        norte: 'Mexico',
        centro: 'Costa Rica',
        sur: 'Argentina'
    },
    {
        norte: 'filipinas',
        centro: 'indonesia',
        sur: 'china'

    }
])

</script>

<style scoped></style>