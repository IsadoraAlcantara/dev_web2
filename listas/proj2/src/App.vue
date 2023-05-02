<script setup>
import { ref } from 'vue'

const quantidade = ref(0)
    const produtos = [
    {
        id: 1,
        nome: 'Camiseta',
        preco: 49.90
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90
    },
    {
        id: 4,
        nome: 'Sapato',
        preco: 199.90
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90
    },
    {
        id: 6,
        nome: 'Óculos',
        preco: 99.90
    },
    {
        id: 7,
        nome: 'Relógio',
        preco: 299.90
    },
    {
        id: 8,
        nome: 'Bermuda',
        preco: 79.90
    },
    {
        id: 9,
        nome: 'Cueca',
        preco: 19.90
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90
    }
]

const carrinho = [
    {
        id: 1,
        nome: 'Camiseta',
        preco: 49.90,
        quantidade: 1,
        valorTotal: 49.90
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90,
        quantidade: 2,
        valorTotal: 199.80
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 4,
        valorTotal: 39.60
    }
]

function total() {
    for (let i = 0; i < carrinho.length; i++) {
        const element = valorTotal[i];
        
    }
}

function adicionar() {
    carrinho.value.push(produto.value)
    carrinho.value = ''
} 

function remover(key) {
    carrinho.value.splice(index, 1)
  }
} 
</script>
<template>
  <ul>
    <li v-for="produto in produtos" :key="produto.id">
      <p>Nome: {{ produto.name }}</p>
      <p>Detalhes</p>
      <p v-for="(produto, key) in produtos" :key="key">{{ produto.key }}</p>
      <button @click="adicionar">+</button>
      <button @click="remover">-</button>
      <p>{{ quantidade }}</p>
    </li>
  </ul>

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
    </select>
  
    <textarea placeholder="hobbies" v-model="hobbies" />
    <p style="white-space: pre-line;"></p>

    <textarea placeholder="biografia" v-model="biografia" />
    <p style="white-space: pre-line;"></p>

    <textarea placeholder="linguagens de programação" v-model="linguagem" />
    <p style="white-space: pre-line;"></p>

    <button type="submit" class="botao">enviar</button>
  </form>
</template>