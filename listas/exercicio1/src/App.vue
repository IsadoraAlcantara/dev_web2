<script setup>

import { ref } from 'vue'

const cidadeNova = ref('')
const cidades = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília'].sort())

function adicionar() {
  cidades.value.push(cidadeNova.value)
  cidadeNova.value = ''
}

</script>
<template>
  <div>
    <button @click="adicionar">Adicionar</button>
  </div>

  <input type="text" v-model="cidadeNova">

  <ul>
    <li v-for="(cidade, i) in cidades" :key="i"> {{ cidade }} </li>
  </ul>
</template>

<style scoped>
button {
    border: none;
    border-radius: 5px;
    font-weight: bold;
    font-size: 16px;
    padding: 7px 20px;
    background-color: #595C48;
    color: aliceblue;
    margin: 5px;
    width: 220px;
}
input {
    padding: 10px;
  border: none;
  margin: 5px;
  outline: none;
  color: grey;
  align-items: center;
  border-radius: 8px;
  background-color: #F2F0EB;
  width: 220px;
}
</style>