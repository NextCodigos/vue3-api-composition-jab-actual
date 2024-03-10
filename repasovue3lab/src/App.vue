<template>

  <!-- <h1 class="" id="" style=""> -->


    <!-- <button @click="">Aceptar</button> -->
    <!-- <button v-on:click="" -->
    
    <!-- Contador -->
    <button @click="decremento">-</button>
    <span>{{ contador }}</span>
    <button @click="incremento">+</button>

</template>


<script setup>
import {ref} from "vue"
const contador=ref(0);
const decremento = () =>{
  contador.value--;
}
const incremento = () =>{
  contador.value++;
}
</script>

<style scoped>
span{
  /* cero arriba abajo y 5 derecha izquierda */
  padding: 0 5px;
}
</style>
