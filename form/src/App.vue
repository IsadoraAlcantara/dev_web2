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
  <div class="container">
    <h2>Formulário</h2>
  <form @submit.prevent="confirmacao = confirma()">
    <input type="text" placeholder="nome" v-model="nome" minlength="3" required/>
    <p></p><input type="email" placeholder="email"  v-model="email" required/>
    <p></p><input type="password" placeholder="senha"  v-model="senha" />
    <p></p><input type="password" placeholder="senha de confirmação"  v-model="senhaConfir" />
    <p></p><input type="date" placeholder="data de nascimento"  v-model="nascimento" />
    <p></p><input type="text" placeholder="endereço" v-model="endereco" />
    <p></p><input type="text" placeholder="cidade" v-model="cidade" />
    <select v-model="estado">
      <option value="" disabled>Estado</option>
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapá</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceará</option>
      <option value="DF">Distrito Federal</option>
      <option value="ES">Espírito Santo</option>
      <option value="GO">Goiás</option>
      <option value="MA">Maranhão</option>
      <option value="MS">Mato Grosso</option>
      <option value="MS">Mato Grosso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Pará</option>
      <option value="PB">Paraíba</option>
      <option value="PR">Paraná </option>
      <option value="PE">Pernambuco</option>
      <option value="PI">Piauí</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande do Norte</option>
      <option value="RS">Rio Grande do Sul </option>
      <option value="RO">Rondônia</option>
      <option value="RR">Roraima</option>
      <option value="SC">Santa Catarina </option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
    </select>
  
    <textarea placeholder="hobbies" v-model="hobbies" />
    <p style="white-space: pre-line;"></p>

    <textarea placeholder="biografia" v-model="biografia" />
    <p style="white-space: pre-line;"></p>

    <textarea placeholder="linguagens de programação" v-model="linguagem" />
    <p style="white-space: pre-line;"></p>

    <button type="submit" class="botao">enviar</button>
  </form>

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
