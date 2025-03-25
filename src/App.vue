<script setup>
import { ref } from 'vue'
const numero = ref(0)
const numeroDois = ref(0)
const total = ref(0)

function aumentar() {
  numero.value++
}
function diminuir() {
  if(numero.value > 0){
    numero.value--
  }
}
function aumentarDois() {
  numeroDois.value++
}
function diminuirDois() {
  if(numeroDois.value > 0){
    numeroDois.value--
  }
}

function somar() {
  total.value = numero.value + numeroDois.value
}
function reiniciar(){
  numero.value=0
  numeroDois.value=0
  total.value=0
}
</script>

<template>
  <h1>Calculadora Soma</h1>
  <div class="Display">
    <div>
      <p>Numero: {{ numero }}</p>
      <button v-on:click="aumentar">+</button>
      <button v-on:click="diminuir">-</button>
    </div>
    <div>
      <p>Numero: {{ numeroDois }}</p>
      <button v-on:click="aumentarDois">+</button>
      <button v-on:click="diminuirDois">-</button>
    </div>
  </div>
  <button v-on:click="somar" class="somar">Calcular</button>
  <button v-on:click="reiniciar">Resetar</button>
  <p class="resultado">A soma é {{ total }}</p>
</template>

<style scoped>
h1{
  margin-left: 0.5vw;
}
div.Display{
  display: flex;
}
div.Display div{
  margin-left: 2vw;
}
button.somar{
  margin-left: 3vw;
}
p.resultado{
  margin-left: 4vw;
}

</style>
