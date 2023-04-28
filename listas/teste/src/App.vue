<script setup>
  import { ref } from 'vue'

  const novoItem = ref('')
  const listaCompras = ref(['arroz', 'batata', 'feijão'])
  
  function adicionar() {
    listaCompras.value.push(novoItem.value)
    novoItem.value = ''
  }

  function remover(index) {
    listaCompras.value.splice(index, 1)
  }

</script>
<template>
  <div>  
  <button @click="adicionar">Adicionar</button>
  <br>
  <button @click="remover(index)">Remover</button>
</div>
  <input type="text" v-model="novoItem">

  <ul>
    <li v-for="(item, i) in listaCompras" :key="i"> {{ item }}</li>
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