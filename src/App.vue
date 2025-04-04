<script setup>
import { computed, ref  } from 'vue'
const contador = ref(0)
const contador2 = ref(0)

function contadorsoma(numero, numero2){
const somaa = numero + numero2;
const booleano1 = true;
return somaa
}

function incrementar() {
  contador.value++
}

function decrementar() {
  if (contador.value !== 0) {
    contador.value--
  }
}

function resetar() {
  contador.value = 0
}

function incrementar2() {
  contador.value++
}

function decrementar2() {
  if (contador.value !== 0) {
    contador.value--
  }
}

function resetar2() {
  contador.value = 0
}
</script>

<template>
  <h1>Contadores</h1>
  <p>Contador 1: {{ contador }}</p>
  <button @click="contador++" class="botao">+</button>
  <button @click="contador--" class="botao">-</button>
  <p>Contador 2: {{ contador2 }}</p>
  <button @click="contador2++" class="botao">+</button>
  <button @click="contador2--" class="botao">-</button>
  <p>{{ contadorsoma(contador,contador2) }}</p>
  <p v-if="contadorsoma(contador, contador2) > 10">Número maior que 10</p>
  <p v-else-if="contadorsoma(contador, contador2) < 10">Número menor que 10</p>
  <p v-else>Número igual a 10</p>
  <p v-if="contadorsoma(contador, contador2) % 2 == 0 "> Número par</p>
  <p v-else>Número impar</p>
  <div >
    <p v-if="12 == contadorsoma(contador, contador2)" style="color: green;">A soma dos números é 12</p>
    <p v-else style="color: red;">A soma dos números é 12</p>
  </div>
  
</template>

<style scoped>
.botao {
  padding: 100px;
}
</style>
