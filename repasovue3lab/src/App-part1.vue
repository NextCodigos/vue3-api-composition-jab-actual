<template>

  <!-- <h1 class="" id="" style=""> -->

  <!-- <h1 :class="selector"> -->
  <h1 v-bind:class="selector">
    Hola {{ miNombre }} y tendré {{ miEdad+1 }}
    </h1>
    <!-- <button @click="">Aceptar</button> -->
    <!-- Funcion saludar -->
    <button v-on:click="saludar(nombre)">Aceptar</button>
</template>


<script setup>
// Ejemplo importar componente
// import HelloWorld from './components/HelloWorld.vue'
const miNombre="Jab"
const nombre="Luis"
const miEdad=18
const miColor="color:green;font-size:3em"
const selector="azul"
const saludar=(nombre)=>{
  console.log(`Hola ${nombre}`)
}
</script>

<style scoped>
.azul{
  color: blue;
}
</style>
