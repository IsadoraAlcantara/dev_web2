<script setup>

const numero = 1
const ok = true
const mensagem = 'programar'



import { ref } from 'vue'
const contador = ref(10)

function incrementar (){
  contador.value++
}

function descrementar (){
  if (contador.value > 0) {
    contador.value--
  }
}

function zerar (){
  if (contador.value > 0) {
    contador.value = 0
  }
}

const rawHtml = '<span style="color: red">Este é um texto em vermelho</span>'

const url = 'https://vuejs.org/'

const nome = 'João'
    const idade = 25

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }

</script>

<template>
  <button @click="incrementar">+</button>
  <button @click="descrementar">-</button>
  <button @click="zerar">c</button>
  <p>Valor do contador: {{ contador }}</p>

  <p>{{ inverter(mensagem) }}</p>

  <p>Usando interpolação de textos: {{rawHtml}}</p>
    <p>Usando v-html: <span v-html="rawHtml"></span></p>

    <span>Valor do contador: {{contador}}</span>

    <div v-if="ok">Mostrar</div>

<p>{{ numero + 1 }}</p>
<p>{{ ok ? 'Sim' : 'Não' }}</p>
<p>{{ mensagem.split('').reverse().join('') }}</p>

<a v-bind:href="url">Mais informações...</a>

<button class="botaoClique" @click="algumaFuncao">Clique aqui</button>

<div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome) }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>

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

.botaoClique {
  background-color: black;
  color: aliceblue;
  width: 60px;
  height: 60px;
  font-size: 10px;
  border-radius: 10px;
}

.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>
