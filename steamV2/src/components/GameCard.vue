<template>
  <div class="game-container">
    <div class="game-title">{{ title }}</div>
    <a :href="link" target="_blank">
      <img :src="imgSrc" :alt="title" />
    </a>
  </div>
  
</template>

<script setup>
defineProps({
  title: String,
  link: String,
  imgSrc: String
})
</script>
