Ejemplos uno por uno separados:

✔ Add ESLint for code quality? … No / Yes

Scaffolding project in /home/next/Música/Vue3-varios/vue3-api-composition-jab-actual/repasovue3lab...

Done. Now run:

  cd repasovue3lab
  npm install
  npm run dev


  ╱  ~/M/V/vue3-api-composition-jab-actual  


///////////////////////////////////////////////////

Ejemplo 1:

App.vue

<!-- Pongo setup evitar poner exportk -->
<script setup>
// Ejemplo importar componente
// import HelloWorld from './components/HelloWorld.vue'

</script>

<template>
  <h1>Hola mundo</h1>
</template>

<style scoped>
h1{
  color: red;
}
</style>




///////////////////////////////////////////////////
///////////////////////////////////////////////////

Ejemplo 2:

<!-- Pongo setup evitar poner export -->
<script setup>
// Ejemplo importar componente
// import HelloWorld from './components/HelloWorld.vue'
const miNombre="Jab"
const miEdad=18
</script>

<template>
  <h1>Hola {{ miNombre }} y tendre {{ miEdad+1 }}</h1>
</template>

<style scoped>
h1{
  color: red;
}
</style>





///////////////////////////////////////////////////
///////////////////////////////////////////////////

style

v-bind:
Creo variable miColor en js y llamo  en html con v:bind:
<h1 v-bind:style="miColor">

///////

<!-- Pongo setup evitar poner export -->
<script setup>
// Ejemplo importar componente
// import HelloWorld from './components/HelloWorld.vue'
const miNombre="Jab"
const miEdad=18
const miColor="color:green;font-size:3em"
</script>

<template>

  <!-- <h1 class="" id="" style=""> -->
  <h1 v-bind:style="miColor">
    Hola {{ miNombre }} y tendré {{ miEdad+1 }}
    </h1>
</template>

<style scoped>

</style>




///////////////////////////////////////////////////
///////////////////////////////////////////////////

class

v-bind:
Creo variable selector en js y llamo  en html con v:bind:
<h1 v-bind:class="selector">

///////

<template>

  <!-- <h1 class="" id="" style=""> -->
  <h1 v-bind:class="selector">
    Hola {{ miNombre }} y tendré {{ miEdad+1 }}
    </h1>
</template>


<script setup>
// Ejemplo importar componente
// import HelloWorld from './components/HelloWorld.vue'
const miNombre="Jab"
const miEdad=18
const miColor="color:green;font-size:3em"
const selector="azul"
</script>

<style scoped>
.azul{
  color: blue;
}
</style>



///////////////////////////////////////////////////
///////////////////////////////////////////////////

v:on para llamar a la funcion desde elemento html,
funcion sin parametro:

<template>

  <!-- <h1 class="" id="" style=""> -->

  <!-- <h1 :class="selector"> -->
  <h1 v-bind:class="selector">
    Hola {{ miNombre }} y tendré {{ miEdad+1 }}
    </h1>
    <!-- <button @click="">Aceptar</button> -->
    <!-- Funcion saludar -->
    <button v-on:click="saludar">Aceptar</button>
</template>


<script setup>
// Ejemplo importar componente
// import HelloWorld from './components/HelloWorld.vue'
const miNombre="Jab"
const miEdad=18
const miColor="color:green;font-size:3em"
const selector="azul"
const saludar=()=>{
  console.log("Hola")
}
</script>

<style scoped>
.azul{
  color: blue;
}
</style>




///////////////////////////////////////////////////
///////////////////////////////////////////////////

v:on para llamar a la funcion desde elemento html,
funcion con parametro:

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




///////////////////////////////////////////////////
///////////////////////////////////////////////////

Variables ref reactivas con ref:


 no tengo importada d error:

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

const contador=0;
const decremento = () =>{
  contador--;
}
const incremento = () =>{
  contador++;
}
</script>

<style scoped>
.azul{
  color: blue;
}
</style>





///////////////////////////////////////////////////
///////////////////////////////////////////////////

Variables ref reactivas con ref:

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





///////////////////////////////////////////////////
///////////////////////////////////////////////////

se mantiene siempre verde los numero dentro de contador:

<template>

  <!-- <h1 class="" id="" style=""> -->


    <!-- <button @click="">Aceptar</button> -->
    <!-- <button v-on:click="" -->
    
    <!-- Contador -->
    <button @click="decremento">-</button>
    <span class="verde">{{ contador }}</span>
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

.rojo{
  color: red;
}
.verde{
  color: green;
}
</style>




///////////////////////////////////////////////////
///////////////////////////////////////////////////

,depende del numero le diga hasta otro 
numero este con un color y cambie a otro color cuando llege
 a otro numero:

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

</template>


<script setup>
import { ref } from "vue"
const miColor = ref("azul")
const contador = ref(0);
const decremento = () => {
  contador.value--;
  if (contador.value<0) {
    miColor.value = "rojo"
  }
}
const incremento = () => {
  contador.value++;
  if (contador.value>5) {
    miColor.value = "verde"
  }
}
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





///////////////////////////////////////////////////
///////////////////////////////////////////////////

v-if elif else se muestre etiqueta o no:

PREGUNTAR no me acaba ir bien

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
    <div v-if="contador<0 ">Escribe una cantidad mayor de 0</div>
      <div v-else-if="contador">Escribe una Cantidad menor que 5</div>
      <div v-else">Escribe una Cantidad menor que 0 o mayor</div>
    <!-- el .value solo utilizamos cuando estamos en script -->
</template>


<script setup>
import { ref } from "vue"
const miColor = ref("azul")
const contador = ref(0);
const decremento = () => {
  contador.value--;
  if (contador.value<0) {
    miColor.value = "rojo"
  }
}
const incremento = () => {
  contador.value++;
  if (contador.value>5) {
    miColor.value = "verde"
  }
}
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



///////////////////////////////////////////////////
///////////////////////////////////////////////////

v-if v-eñse se muestre etiqueta o no:

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
    <div v-if="contador<0 ">Escribe una cantidad mayor de 0</div>
      <div v-else>Escribe una Cantidad menor que 5</div>
    <!-- el .value solo utilizamos cuando estamos en script -->
</template>


<script setup>
import { ref } from "vue"
const miColor = ref("azul")
const contador = ref(0);
const decremento = () => {
  contador.value--;
  if (contador.value<0) {
    miColor.value = "rojo"
  }
}
const incremento = () => {
  contador.value++;
  if (contador.value>5) {
    miColor.value = "verde"
  }
}
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



///////////////////////////////////////////////////
///////////////////////////////////////////////////

v-if v-else-if:

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
    <div v-if="contador<0 ">Escribe una cantidad mayor de 0</div>
      <div v-else-if="contador>=5">Escribe una Cantidad menor que 5</div>

    <!-- el .value solo utilizamos cuando estamos en script -->
</template>
a

<script setup>
import { ref } from "vue"
const miColor = ref("azul")
const contador = ref(0);
const decremento = () => {
  contador.value--;
  if (contador.value<0) {
    miColor.value = "rojo"
  }
}
const incremento = () => {
  contador.value++;
  if (contador.value>5) {
    miColor.value = "verde"
  }
}
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




///////////////////////////////////////////////////

v-show ejejmplo 1 se ve siempre y se añade a los otros valores o no 
se ve nunca:

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
  <div v-show="visible">No esta permitido el numero 0</div>

  <!-- el .value solo utilizamos cuando estamos en script -->
</template>
a

<script setup>
import { ref } from "vue"
const visible=false
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




///////////////////////////////////////////////////
///////////////////////////////////////////////////

v-show dinamico sin propiedades computadas:

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
  <div v-show="visible">No esta permitido el numero 0</div>

  <!-- el .value solo utilizamos cuando estamos en script -->
</template>
a

<script setup>
import { ref } from "vue"
const visible=ref(true)
const miColor = ref("azul")
const contador = ref(0);
const decremento = () => {
  contador.value--;
  if (contador.value < 0) {
    miColor.value = "rojo"
  }
  visible.value=contador.value===0;
}
const incremento = () => {
  contador.value++;
  if (contador.value > 5) {
    miColor.value = "verde"
  }
  visible.value=contador.value===0;
}
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




///////////////////////////////////////////////////
///////////////////////////////////////////////////

v-show dinamico con propiedades computadas se guarda en cahe la funcion norma no:

IMAGENES desde url 1:


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
  <img src="https://www.html6.es/img_html/micanalyoutube.png" alt="">
  <!-- el .value solo utilizamos cuando estamos en script -->
</template>
a

<script setup>
import { ref,computed } from "vue"
// const visible=ref(true)
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





///////////////////////////////////////////////////
///////////////////////////////////////////////////

IMAGENES desde url 2:


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
  <!-- el .value solo utilizamos cuando estamos en script -->
</template>
a

<script setup>
import { ref,computed } from "vue"
// const visible=ref(true)
const imagen1 ="https://www.html6.es/img_html/micanalyoutube.png"
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



///////////////////////////////////////////////////
///////////////////////////////////////////////////

voy minuto 40:33 empieza desde cero vu3 jab api composition

Imagenes desde assets y carpeta public:


///////////////////////////////////////////////////
///////////////////////////////////////////////////


Imagenes desde assets y carpeta public:

App.vue

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
  <!-- el .value solo utilizamos cuando estamos en script -->
</template>
a

<script setup>
import { ref,computed } from "vue"
// desde carpeta assets hay que importar
import imagen2 from "./assets/logo.svg"
// const visible=ref(true)
const imagen1 ="https://www.html6.es/img_html/micanalyoutube.png"
// abajo de este mas corto y funciona
// const imagen3 ="../public/rey_ervigio.png"
const imagen3 ="rey_ervigio.png"
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



///////////////////////////////////////////////////
///////////////////////////////////////////////////

Imagenes importadas desde archivo datos.js

App.vue

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


///////////////

datos.js

export const valores=[
    {web:"https://www.html6.es/img_html/micanalyoutube.png"}
]

