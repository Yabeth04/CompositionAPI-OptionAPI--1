<template>
    <form>
        <input type="text" v-model="mostrarMensage">
        <input type="checkbox" v-model="terminos"> terminos y condiciones
        <h3> {{ mostrarMensage }}</h3>
        <select v-model="country">
            <option value="0" disabled>Seleccionar</option>
            <option value="1">Costa Rica</option>
            <option value="2">Alemania</option>
            <option value="3">Estonia</option>
        </select>
    </form>
</template>

<script setup>
    import {ref} from 'vue'

    let mostrarMensage = ref('')
    let terminos = ref(false)
    let country = ref('0')


</script>

<style>

</style>