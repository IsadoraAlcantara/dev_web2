<script setup>
import { ref } from 'vue'

const novoItem = ref({
    id: 0,
    nome: '',
    preco: 0,
    quantidade: 1,
})

const produtos = ref([
  {
    id: 1,
    nome: 'Camiseta',
    preco: 49.9,
    quantidade: 0,
    imagem: "https://assets.stickpng.com/images/580b57fbd9996e24bc43bf78.png"
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

function diminuir(id) {
  if (produtos.value[id].quantidade > 0) {
    produtos.value[id].quantidade--;
  }
}

function adicionarCarrinho(index) {
  if (produtos.value[index].quantidade > 0) {
    novoItem.value.id = produtos.value[index].id;
    novoItem.value.nome = produtos.value[index].nome;
    novoItem.value.preco = produtos.value[index].preco;
    novoItem.value.quantidade = produtos.value[index].quantidade;
    carrinho.value.push({ ...novoItem.value });
  }
  else {
    alert("Selecione a quantidade do produto desejado")
  }

}

function removerCarrinho(index) {
  carrinho.value.splice(index, 1)
}
</script>
<template>
  <ul class="produtos-main">
    <h2>Produtos</h2>

    <div class="descricao">
      <section>
        <table>
          <thead>
            <tr>
              <th>Protudo</th>
              <th>Preço</th>
              <th>Valor total</th>
              <th>Quantidade</th>
            </tr>
          </thead>
          <tbody>
            <td></td>
            <td>R$:49.9</td>
            <td></td>
            <td></td>
            <td></td>
          </tbody>
        </table>
      </section>


    </div>

    <li class="produtos-item" v-for="(produto, index) in produtos" :key="index">
      <div>
        <img src=produto.imagem alt="">
      </div>
      <div>
        <p>Nome: {{ produto.nome }}</p>
      </div>
      <div>
        <p>Preço: R$:{{ produto.preco }}</p>
      </div>
      <div>
        <p>Valor Total: R$:{{ produto.valorTotal }}</p>
      </div>
      <p v-for="(produto, key) in produtos" :key="key">{{ produto.key }}</p>
      <div class="bt">
        <button class="btMaisMenos" @click="produto.quantidade++">+</button>
        <p>{{ produto.quantidade }}</p>
        <button class="btMaisMenos" @click="diminuir(produto.id - 1)">-</button>
      </div>
      <div>
        <button class="btCarrinho" @click="adicionarCarrinho(index)">Adicionar</button>
      </div>
    </li>
  </ul>

  <ul class="carrinho">
    <h2>Carrinho</h2>

    <li class="item" v-for="(produto, index) in carrinho" :key="index">
      <div>
        <img src=produto.imagem alt="">
      </div>
      <div>
        <p>Nome: {{ produto.nome }}</p>
      </div>
      <div>
        <p>Preço: R$:{{ produto.preco }}</p>
      </div>
      <div>
        <p>Valor Total: R$:{{ produto.valorTotal }}</p>
      </div>
      <p v-for="(produto, key) in produtos" :key="key">{{ produto.key }}</p>
      <div>
        <button class="btCarrinho" @click="remover(index)">Remover</button>
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

.carrinho {
  font-size: 18px;
  background-color: #E8E9E4;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 80px;
  border-radius: 15px;
  box-shadow: 0px 10px 40px #00000056;
  width: 700px;
  height: auto;
  color: black;
}

li {
  list-style: none;
  justify-content: space-around;
  display: flex;
}

.produtos-main {
  color: black;
  padding: 0 30px;
  width: 900px;
  height: min-content;
  align-items: center;
  font-size: 18px;
  background-color: #E8E9E4;
  top: 50%;
  left: 30%;
  transform: translate(-50%, -50%);
  padding: 80px;
  border-radius: 15px;
  box-shadow: 0px 10px 40px #00000056;
  color: black;
  margin: 10px 5px;
}

.bt {
  background-color: #ccc;
  display: inline-flex;
  align-items: center;
  padding: 5px 0;
  justify-content: space-around;
  min-width: 60px;
  border-radius: 20px;
}

.btMaisMenos {
  background: transparent;
  border: none;
  align-items: center;
  padding: 0 10px;
  font-size: 20px;
  margin: 10px 5px;
}

.btCarrinho {
  border: none;
  border-radius: 5px;
  font-weight: bold;
  font-size: 16px;
  padding: 7px 20px;
  background-color: ccc;
  color: black;
  margin: 10px 5px;
  width: 150px;
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

.item {
  background-color: white;
  position: relative;
  width: 100%;
  margin: 30px 0;
  border-radius: 8px;
  box-shadow: 0 4px 18px #2a2f430f;
  justify-content: space-around;
}
</style>