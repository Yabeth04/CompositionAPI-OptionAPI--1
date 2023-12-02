<template>
    <section class="addprof">
        <h1>Agregar Profesor</h1>
        <form>
            <input type="text" placeholder="Nombre" v-model="nombre" @input="validarLetras">
            <input type="text" placeholder="Apellidos" v-model="apellido" @input="validarLetras">
            <input type="text" placeholder="cedula" v-model="cedula" @input="validarEdad" maxlength="9">
            <br>
            <input type="text" placeholder="Especialidad" v-model="especialiadad" @input="validarLetras">
            <input type="text" placeholder="Edad" v-model="edad" @input="validarEdad" maxlength="2">
            <input type="text" placeholder="Materias" v-model="materias" @input="validarLetras">
            <br>
            <div class="box_docu">
                <h3>Documentacion</h3>
                <input type="checkbox" v-model="documentacion">
            </div>
        </form>
        <button @click.prevent="enviarDatos">Agregar</button>
    </section>
    <section class="table">
        <table>
            <thead>
                <td>Nombre</td>
                <td>Apellidos</td>
                <td>Edad</td>
                <td>Cedula</td>
                <td>Especialiadad</td>
                <td>Materias</td>
                <td class="ultima">Documentacion</td>
            </thead>
            <tbody>
                <tr v-for="(profesor, index) in profesores" :key="index">
                    <td>{{ profesor.nombre }}</td>
                    <td>{{ profesor.apellido }}</td>
                    <td>{{ profesor.edad }}</td>
                    <td>{{ profesor.cedula }}</td>
                    <td>{{ profesor.especialiadad }}</td>
                    <td>{{ profesor.materias }}</td>
                    <td>{{ profesor.documentacion ? 'Entregado' : 'No entregado' }}</td>
                </tr>
            </tbody>
        </table>
    </section>
</template>

<script setup>
import { ref } from 'vue'

let profesores = ref([])
let materias = ref('')
let nombre = ref('')
let apellido = ref('')
let edad = ref('')
let cedula = ref('')
let especialiadad = ref('')
let documentacion = ref(false)

function validarLetras() {
    //el símbolo ^ busca cualquier caracter que NO esté en la lista
    //y g es un modificador global,  indica que la búsqueda debe realizarse globalmente en toda la cadena, no solo en la primera coincidencia.
    nombre.value = nombre.value.replace(/[^A-Za-z && '']/g, '')
    materias.value = materias.value.replace(/[^A-Za-z && '']/g, '')
    apellido.value = apellido.value.replace(/[^A-Za-z && '']/g, '')
    especialiadad.value = especialiadad.value.replace(/[^A-Za-z && '']/g,'')
}
function validarEdad() {
    // Elimina cualquier caracter no numérico
    edad.value = edad.value.replace(/\D/g, '');
    cedula.value = cedula.value.replace(/\D/g,'')
}



function enviarDatos() {
    if (nombre.value === '' || edad.value === '' || apellido.value === '' || materias.value === '') {
        alert('completa el formulario')
    } else {
        profesores.value.push({
            nombre: nombre.value,
            apellido: apellido.value,
            edad: edad.value,
            materias: materias.value,
            documentacion: documentacion.value,
            especialiadad: especialiadad.value,
            cedula: cedula.value
        });
    }
    nombre.value = ''
    apellido.value = ''
    edad.value = ''
    materias.value = ''
    documentacion.value = ''
    especialiadad.value = ''
    cedula.value = ''
}
</script>

<style scoped>
table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

th,
td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: left;
}

th {
    background-color: #f2f2f2;
}

*{
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.ultima{
    width: 130px;
}

thead{
    background-color: rgb(142, 142, 142);
    color: white;
    font-weight: bold;
}
.table{
    background-color: #f1f1f1;

}
.addprof{
    height: 30vh;
    justify-content: center;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.box_docu{
    display: flex;
    align-items: center;
    justify-content: center;
}

.box_docu h3{
    margin-right: 5px;
}

form button{
    align-items: center;
    justify-content: center;
    display: flex;
    flex-direction: column;
}

input, h3, button{
    margin: 10px;
}

input{
    border-radius: 5px;
    padding: 6px;
    border: 1px solid black;
}

input[type="text"]:focus{
    appearance: none;
  outline: none;
  box-shadow: 0 0 5px rgb(104, 104, 104); /* Agregar sombra al enfocar */
}


button{
    background-color: transparent;
    padding: 4px 12px;
    border-radius: 6px;
    border: 2px solid rgb(0, 0, 0);
    font-weight: bold;
}

button:hover{
    background-color: rgb(0, 212, 0);
    border: 2px solid white;
    color: white;
}
</style>
