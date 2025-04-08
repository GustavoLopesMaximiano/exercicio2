<script setup>
import { computed, ref } from 'vue'
const contador = ref(0)
const contador2 = ref(0)
const valorbooleano = ref(true)

function contadorsoma(numero, numero2) {
  const somaa = numero + numero2
  
  return somaa
}
function fatos(somaoriginal) {
  if (somaoriginal % 2 == 0) {
    return alert("O número é par")
  }
  else {
    return alert("O número é ímpar")

  }

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
  contador2.value++
}

function decrementar2() {
  if (contador2.value !== 0) {
    contador2.value--
  }
}

function resetar2() {
  contador2.value = 0
}
</script>

<template>
  <h1>Contadores</h1>
  <p>Contador 1: {{ contador }}</p>
  <button @click="incrementar" class="botao">+</button>
  <button @click="decrementar" class="botao">-</button>
  <button @click="resetar" class="botao">Resetar</button>
  <p>Contador 2: {{ contador2 }}</p>
  <button @click="incrementar2" class="botao">+</button>
  <button @click="decrementar2" class="botao">-</button>
  <button @click="resetar2" class="botao">Resetar</button> <br>
  <button @click="fatos(contadorsoma(contador, contador2))" class="botao">A soma dos números é par ou ímpar?</button>
  <button @click="valorbooleano = !valorbooleano" class="botao">{{ valorbooleano ? 'Esconder Resultado' : 'Mostrar Resultado' }}</button>
  
  <p v-if="valorbooleano == true">{{ contadorsoma(contador, contador2) }}</p>
  <p v-if="contadorsoma(contador, contador2) > 10">Número maior que 10</p>
  <p v-else-if="contadorsoma(contador, contador2) < 10">Número menor que 10</p>
  <p v-else>Número igual a 10</p>
  
  <div>
    <p v-if="12 == contadorsoma(contador, contador2)" style="color: green">
      A soma dos números é 12
    </p>
    <p v-else style="color: red">A soma dos números é 12</p>
  </div>
</template>

<style scoped>
.botao {
  padding: 100px;
}
</style>
