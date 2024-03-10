<template>

  <!-- <h1 class="" id="" style=""> -->


  <!-- <button @click="">Aceptar</button> -->
  <!-- <button v-on:click="" -->

  <!-- <h1 :class="selector"> -->
  <!-- <h1 v-bind:class="selector"> -->

  <!-- Contador -->
  <button @click="decremento">-</button>
  <span :class="miColor">{{ contador }}</span>
  <button @click="incremento">+</button>
  <div v-if="contador < 0">Escribe una cantidad mayor de 0</div>
  <div v-else-if="contador >= 5">Escribe una Cantidad menor que 5</div>
  <div v-show="comprobacion">No esta permitido el numero 0</div>
  <img :src="imagen1" alt="">
  <img :src="imagen2" alt="">
  <img :src="imagen3" alt="">
  <img :src="imagen4" alt="">
  <!-- el .value solo utilizamos cuando estamos en script -->
</template>
a

<script setup>
import { ref,computed } from "vue"
import {valores} from "./datos"
// desde carpeta assets hay que importar
import imagen2 from "./assets/logo.svg"
// const visible=ref(true)
const imagen1 ="https://www.html6.es/img_html/micanalyoutube.png"
// abajo de este mas corto y funciona
// const imagen3 ="../public/rey_ervigio.png"
const imagen3 ="rey_ervigio.png"
const imagen4="valores[0].vue"
const miColor = ref("azul")
const contador = ref(0);
const decremento = () => {
  contador.value--;
  if (contador.value < 0) {
    miColor.value = "rojo"
  }
  
}
const incremento = () => {
  contador.value++;
  if (contador.value > 5) {
    miColor.value = "verde"
  }
  
}
const comprobacion=computed(()=>{
  // si se cumple condicion true o false
  return contador.value === 0;
})
</script>

<style scoped>
span {
  /* cero arriba abajo y 5 derecha izquierda */
  padding: 0 5px;
}

.rojo {
  color: red;
}

.verde {
  color: green;
}

.azul {
  color: blue;
}
</style>
