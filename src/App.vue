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
  <button v-on:click="somar">Calcular</button>
  <p>A soma é {{ total }}</p>
</template>

<style scoped>
h1{
  margin-left: 2vw;
}
div.Display{
  display: flex;
}
div.Display div{
  margin-left: 2vw;
}
</style>
