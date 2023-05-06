<script setup>
import { ref } from 'vue'

const produtos = ref([
  {
    id: 1,
    nome: 'Camiseta',
    preco: 49.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 2,
    nome: 'Calça',
    preco: 99.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 3,
    nome: 'Meia',
    preco: 9.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 4,
    nome: 'Sapato',
    preco: 199.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 5,
    nome: 'Boné',
    preco: 29.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 6,
    nome: 'Óculos',
    preco: 99.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 7,
    nome: 'Relógio',
    preco: 299.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 8,
    nome: 'Bermuda',
    preco: 79.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 9,
    nome: 'Cueca',
    preco: 19.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
  {
    id: 10,
    nome: 'Meia',
    preco: 9.9,
    quantidade: 0,
    imagem: "imagens/camiseta.png" 
  },
])

const carrinho = [
  {
    id: 1,
    nome: 'Camiseta',
    preco: 49.9,
    quantidadeCarrinho: 1,
    valorTotal: 49.9
  },
  {
    id: 2,
    nome: 'Calça',
    preco: 99.9,
    quantidadeCarrinho: 2,
    valorTotal: 199.8
  },
  {
    id: 3,
    nome: 'Meia',
    preco: 9.9,
    quantidadeCarrinho: 4,
    valorTotal: 39.6
  }
]

function total() {
  for (let i = 0; i < carrinho.length; i++) {
    const valorTotal = valorTotal[i] + valorTotal
  }
}

function diminuir(idProd) {
  if (produtos.value[idProd].quantidade > 0) {
    produtos.value[idProd].quantidade--
  }
}

function adicionarCarrinho() {
  carrinho.value.push(produtos.value)
  carrinho.value = ''
}

function removerCarrinho(key) {
  carrinho.value.splice(index, 1)
}
</script>
<template>
  <ul class="produtos-main">
    <h2>Produtos</h2>

    <li class="produtos-item" v-for="(produto, index) in produtos" :key="index">
        <div><p>Imagem: {{ produto.imagem }}</p></div>
        <div><p>Nome: {{ produto.nome }}</p></div>
        <div><p>Preço: R$:{{ produto.preco }}</p></div>
        <div><p>Valor Total: R$:{{ produto.valorTotal }}</p></div>
      <p v-for="(produto, key) in produtos" :key="key">{{ produto.key }}</p>
      <div class="bt">
        <button class="bt-prod" @click="produto.quantidade++">+</button>
      <p>{{ produto.quantidade }}</p>
      <button class="bt-prod" @click="diminuir">-</button>
      </div>
    </li>
  </ul>
</template>
<style scoped>
.botao {
  border: none;
  border-radius: 5px;
  font-weight: bold;
  font-size: 16px;
  padding: 7px 20px;
  background-color: #595c48;
  color: aliceblue;
  margin: 5px;
  width: 220px;
}
.container {
  font-size: 18px;
  background-color: #253b35;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 80px;
  border-radius: 15px;
  box-shadow: 0px 10px 40px #00000056;
  width: 400px;
  color: black;
}

li {
  list-style: none;
  justify-content: space-around;
  display: flex;
}

.produtos-main {
  color: black;;
  padding: 0 30px;
  width: 700px;
  height: min-content;
  align-items: center;
  font-size: 18px;
  background-color: #E8E9E4;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 80px;
  border-radius: 15px;
  box-shadow: 0px 10px 40px #00000056;
  color: black;
}

.bt {
  background-color: #ccc;
  display: inline-flex;
  align-items: center;
  padding: 5px 0;
  justify-content: space-around;
  min-width: 60px;
  border-radius: 20px;

  .bt-prod {
    background: transparent;
    border: 0;
    align-items: center;
    padding: 0 10px;
  }
}

h2 {
  padding: 50px 0;
  text-align: center;
  font-size: 40px;
}

.produtos-main .produtos-item {
    background-color: white;
    position: relative;
    width: 100%;
    margin: 30px 0;
    border-radius: 8px;
    box-shadow: 0 4px 18px #2a2f430f;
    justify-content: space-around;
}

</style>