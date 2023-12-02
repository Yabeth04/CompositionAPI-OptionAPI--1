<template>

    <div class="box">
        <form >
            <input type="text" v-model="this.inputText">
            <input type="checkbox" v-model="trueOrFalse"> acepto los terminos y condiciones
            <h2>{{ this.inputText }}</h2>
        </form>
        <h3>{{ mostrarMensage() }} </h3>
    </div>
</template>

<script >

export default {
    data() {
        return{
            name: 'ModeloForm',
            inputText:'',
            trueOrFalse: false,
            terminos:'haz aceptado los terminos',
        }
    },
    methods:{
        cambioTxt(){
            this.inputText = ''
        },

        mostrarMensage(){
            if(this.trueOrFalse === true){
                return 'Terminos aceptados'
            }else {

            }
        }
    }
    

}


</script>

<style scoped>
.box{
    justify-content: space-between;
    display: flex;
}

h3{
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    color: green;
}
</style>