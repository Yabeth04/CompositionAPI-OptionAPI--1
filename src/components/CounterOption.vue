<template>
    <div class="fondo">
        <h2>Practica 2</h2>
        <h2>Option API</h2>
        <h3>{{ counter }}</h3>
        <div class="box-btn">
            <button @click="funcionIncrementar">Incrementar</button>
            <button @click="funcionDecrementar">Decrementar</button>
        </div>
    </div>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'counterOption',
    components: {},
    data() {
        var counter = 0;
        return { counter }
    },
    methods: {
        funcionIncrementar() {
            this.counter++
        },
        funcionDecrementar(){
            this.counter--
        }
    }
})

</script>

<style scoped>


.fondo {
    margin-top: 20px;
    font-family:system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    height: 45vh;
    background-color: rgb(238, 238, 238);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
h3{
    border-radius: 10px;
    background-color: rgb(222, 222, 222);
    width: 100px;
    text-align: center;
    padding: 5px 20px;
    font-size: 30px;
}


</style>