<script setup>
import { ref } from 'vue'

const contador = ref(0)
const contador2 = ref(0)

function incrementar() {
  contador.value++
}

function desencrementar() {
  contador.value--
}

function incrementar2() {
  contador2.value++
}

function decrementar2() {
  contador2.value--
}

function soma() {
  return contador.value + contador2.value

}

</script>

<template>
  <div>
    <button>{{ contador }} </button>
      <button @click="incrementar">+</button>
      <button @click="desencrementar">-</button>
  </div>
  <div>
    <button>{{ contador2 }} </button>
      <button @click="incrementar2">+</button>
      <button @click="decrementar2">-</button>
  </div>

    <span v-if="soma() > 10">soma dos contadores maior do que 10. Soma dos contadores:  {{ soma() }}</span>
    <span v-else-if="soma() < 10">soma dos contadores menor do que 10.  Soma dos contadores: {{ soma() }}</span>
    <span v-else>Soma dos contadores: {{ soma() }}</span>

    <span v-if="soma() % 2 == 0">O contador é par</span>


</template>

<style scoped>

  button {
  width: 60px;
  height: 60px;
  background-color: black;
  color:aliceblue;
  font-size: 50px;
  border: none;
  border-radius: 50%;
  margin-bottom: 20px;
  margin-left: 20px; 
}
</style>
