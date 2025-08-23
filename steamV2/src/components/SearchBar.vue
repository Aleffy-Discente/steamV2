<template>
  <div class="pesquisa">
    <form class="pesquisa-form" @submit.prevent>
      <input
        type="search"
        id="search-bar"
        placeholder="Buscar..."
        class="busca-form"
        v-model="model"
      />
      <button type="button" class="busca-button" @click="model = ''">Limpar</button>
    </form>
  </div>
</template>

<script setup>
const model = defineModel({ type: String, default: '' })
</script>
