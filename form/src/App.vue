<script setup>
import { ref, computed } from 'vue'

const nome = ref('');
const email = ref('');
const senha = ref('');
const senhaConfir = ref('');
const nascimento = ref('');
const endereco = ref('');
const cidade = ref('');
const estado = ref('');
const hobbies = ref('');
const biografia = ref('');
const linguagem = ref('');
const confirmacao = ref(false);


function confirma() {
  if (nome.value.length <= 20 && senha.value == senhaConfir.value) {
    return true;
  }
}

</script>

<template>


</div>
<div class="final" v-if="confirmacao">
  <h2>Respostas</h2>
  <p>Nome: {{ nome }}</p>
  <p>Email: {{ email }}</p>
  <p>Senha: {{ senha }}</p>
  <p>Data de nascimento: {{ nascimento }}</p>
  <p>Endereço: {{ endereco }}</p>
  <p>Cidade: {{ cidade }}</p>
  <p>Estado: {{ estado }}</p>
  <p>hobbies: {{ hobbies }}</p>
  <p>biografia: {{ biografia }}</p>
  <p>Linguagens de programação: {{ linguagem }}</p>
</div>
</template>

<style scoped>

body {
    background-color: aquamarine;
}
.botao {
  border: none;
    border-radius: 5px;
    font-weight: bold;
    font-size: 16px;
    padding: 7px 20px;
    background-color: #595C48;
    color: aliceblue;
    margin: 5px;
    width: 220px;
    position: absolute;
}
.final {
  font-size: 18px;
    background-color: #253B35;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 80px;
    border-radius: 15px;
    box-shadow: 0px 10px 40px #00000056;
    width: 500px;
}

input, textarea, select{
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

p {
  color: #F3E4B3;
}
.container {
    font-size: 18px;
    background-color: #253B35;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 80px;
    border-radius: 15px;
    box-shadow: 0px 10px 40px #00000056;
    width: 400px;
  }

  h2 {
    color: #F3E4B3;
    text-align: center;
  }
</style>
