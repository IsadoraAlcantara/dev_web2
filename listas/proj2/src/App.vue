<script setup>
import { ref } from 'vue'

const contador = ref(0)
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

</script>
<template>
    <ul>
        <h2>Produtos</h2>
        <li v-for="produto in produtos" :key="produto.id">
            <p>Nome: {{ produto.name }}</p>
            <p>Detalhes</p>
            <p v-for="(produto, key) in produtos" :key="key">{{ produto.key }}</p>
            <button @click="adicionar">+</button>
            <button @click="remover">-</button>
            <p>{{ contador }}</p>
        </li>
    </ul>

    <div class="container">
        <h2>Carrinho</h2>
        <p>{{ total }}</p>
            <button type="submit" class="botao">finalizar compra</button>
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
    color: aliceblue;
  }

  li {
    list-style: none;
  }
</style>