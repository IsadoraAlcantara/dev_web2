<script setup>
import { ref } from 'vue'
// fazer carrinho vazio <3
const confirmacao = ref(false);
const novoItem = ref({
  id: 0,
  nome: '',
  preco: 0,
  quantidade: 1,
  valorTotal: 0
})

const produtos = ref([
  {
    id: 1,
    nome: 'Camiseta',
    preco: 49.9,
    quantidade: 0,
    imagem: "https://images.tcdn.com.br/img/img_prod/275189/camisa_azul_royal_100_poliester_para_sublimacao_g_2703_1_20200722153139.jpg",
    valorTotal: 0
  },
  {
    id: 2,
    nome: 'Calça',
    preco: 99.9,
    quantidade: 0,
    imagem: "https://images.tcdn.com.br/img/img_prod/652999/calca_tactel_cargo_street_caqui_box_logo_4918_1_ed10b74fdd51144c7d2abe1a7adf9378.jpg"
  },
  {
    id: 3,
    nome: 'Meia',
    preco: 9.9,
    quantidade: 0,
    imagem: "https://decathlonpro.vtexassets.com/arquivos/ids/2097317/--meia-btwin-preta-500-uk25-5-us3-551.jpg?v=636662999313100000"
  },
  {
    id: 4,
    nome: 'Sapato',
    preco: 199.9,
    quantidade: 0,
    imagem: "data:image/jpeg;base64,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"
  },
  {
    id: 5,
    nome: 'Boné',
    preco: 29.9,
    quantidade: 0,
    imagem: "https://images-americanas.b2w.io/produtos/2960616224/imagens/bone-aba-curva-liso-preto/2960616232_1_large.jpg"
  },
  {
    id: 6,
    nome: 'Óculos',
    preco: 99.9,
    quantidade: 0,
    imagem: "https://images.tcdn.com.br/img/img_prod/810719/oculos_de_sol_oakley_quadrado_oo9018_ojector_3191_1_8d7b4a0542f8b5ebf1be0315fd8b4edb.jpg"
  },
  {
    id: 7,
    nome: 'Relógio',
    preco: 299.9,
    quantidade: 0,
    imagem: "https://images.tcdn.com.br/img/img_prod/740836/smartwatch_d13_relogio_de_pulso_inteligente_9987_1_2a7f1262539b54707d08e19ae566f0dd.png"
  },
  {
    id: 8,
    nome: 'Bermuda',
    preco: 79.9,
    quantidade: 0,
    imagem: "https://images.tcdn.com.br/img/img_prod/652999/bermuda_cargo_moletom_preta_box_logo_4713_1_692c62e44718f74a18bf45a31458ffd9.jpg"
  },
  {
    id: 9,
    nome: 'Cueca',
    preco: 19.9,
    quantidade: 0,
    imagem: "https://trackfield.vtexassets.com/arquivos/ids/241928/cueca-slip-masculina-de-algodao-mescla-cinza-frente.jpg?v=637753654775630000"
  },
  {
    id: 10,
    nome: 'Meia',
    preco: 9.9,
    quantidade: 0,
    imagem: "https://cdn.shopify.com/s/files/1/0019/1604/3327/products/meia-cano-alto-lilo-rosto-min_2000x.png?v=1601298613"
  },
])

const carrinho = ref([])

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
    novoItem.value.valorTotal = produtos.value[index].quantidade * produtos.value[index].preco; 
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

    <div class="descricao" >
      <section>
        <table>
          <thead>
            <tr>
              <th>Produto</th>
              <th>Preço</th>
              <th>Valor total</th>
              <th>Quantidade</th>
            </tr>
          </thead>
          <tbody class="produtos-item" v-for="(produto, index) in produtos" :key="index">
            <td>{{produto.nome   }}</td>
            <td>{{ produto.preco }}</td>
            <td>{{ (produto.quantidade * produto.preco).toFixed(2) }}</td>
            <td>{{ produto.quantidade }}</td>
            <td></td>
          </tbody>
        </table>
      </section>


    </div>

    <li class="produtos-item" v-for="(produto, index) in produtos" :key="index">
      <div>
        <img :src="produto.imagem" alt="">
      </div>
      <div>
        <p>{{ produto.nome }}</p>
      </div>
      <div>
        <p>R$:{{ produto.preco }}</p>
      </div>
      <div>
        <p>{{ (produto.quantidade * produto.preco).toFixed(2) }}</p>
      </div>
      <p v-for="(produto, index) in produtos" :key="index">{{ produto.index }}</p>
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

    <div class="descricao">
      <section>
        <table>
          <thead>
            <tr>
              <th>Produto</th>
              <th>Preço</th>
              <th>Valor total</th>
              <th>Quantidade</th>
            </tr>
          </thead>
        </table>
      </section>
    </div>

    <li class="item" v-for="(produto, index) in carrinho" :key="index">
      <div>
        <img src=produto.imagem alt="">
      </div>
      <div>
        <p> {{ produto.nome }}</p>
      </div>
      <div>
        <p> R$:{{ produto.preco }}</p>
      </div>
      <div>
        <p>R$:{{ produto.valorTotal }}</p>
      </div>
      <div>
        <p>{{ produto.quantidade }}</p>
      </div>
      <p v-for="(produto, index) in produtos" :key="index">{{ produto.index }}</p>
      <div>
        <button class="btCarrinho" @click="removerCarrinho(index)">Remover</button>
      </div>
    </li>
  </ul>
</template>
<style scoped>
img {
  max-width: 100px;
}

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
  padding: 0 10px;
  justify-content: space-around;
  min-width: 60px;
  border-radius: 20px;
  margin: 10px 5px;
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
  align-items: center;
}

.item {
  background-color: white;
  position: relative;
  width: 100%;
  margin: 30px 0;
  border-radius: 8px;
  box-shadow: 0 4px 18px #2a2f430f;
  justify-content: space-around;
  align-items: center;
}

.descricao {
}
</style>