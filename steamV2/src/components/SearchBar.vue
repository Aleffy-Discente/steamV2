<template>
  <div class="pesquisa">
    <form class="pesquisa-form" @submit.prevent>
      <input type="search" id="search-bar" placeholder="Buscar..." class="busca-form" v-model="query">
      <button type="button" class="busca-button" @click="search">Pesquisar</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const query = ref('')

function search() {
  console.log('Buscando por:', query.value)
}
</script>
