<script setup>
  import { ref } from 'vue'

const novoItem = ref('')
const listaCompras = ref(['arroz', 'batata', 'feijão'])

function adicionar() {
  listaCompras.value.push(novoItem.value)
  novoItem.value = ''
}
</script>

<template>
  <input type="text" v-model="novoItem">
  <button @click="adicionar">Adicionar</button>
  <ul>
    <li v-for="item in lista">{{ item }}</li>
  </ul>
</template>

<style scoped>
</style>
