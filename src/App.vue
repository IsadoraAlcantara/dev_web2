<script setup>
import {livros} from '@/_data/livros'
</script>

<template>
  <h1>Minha livraria</h1>
  <div class="listagem-livros">
    <div v-for="livro in livros" :key="livro.id" class="card-livro">
      <img :src="livro.cover" alt="" class="livro-capa"/>
      <p class="livro-titulo">{{ livro.title }}</p>
      <p class="livro-autor">{{ livro.author }}</p>
      <p class="livro-preco">{{ livro.price }}</p>
    </div>
  </div>
</template>

<style scoped>
.livro-capa {
  width: 200px;
}
.card-livro {
  background-color: beige;
  padding: 10px;
  border-radius: 10px;
  width: 200px;
  margin: 10px;
}

.listagem-livros {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.listagem-livros p {
  margin: 0;
}

.listagem-livros .livro-titulo {
  font-weight: bold;
  font-size: 1 2.rem;
  margin-bottom: 5px;
}
</style>
