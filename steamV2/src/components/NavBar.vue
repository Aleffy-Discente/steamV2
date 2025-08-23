<template>
  
  <nav class="navbar">
    <div class="logo">
      <img style="margin-left: 40px;" class="logo_imagem" src="/steamV2/public/imgs/fav.png" alt="logo">
      <p class="game-logo">Game<span class="hub-logo selecionado">Hub</span></p>
    </div>
    <div class="navv">
      <div class="opcoes">
        <a class="filtro plataforma" id="pc" href="#" @click="alerta()">PC</a>
        <p>|</p>
        <a class="filtro plataforma" id="browser" href="#" @click="alerta()">Browser</a>
        <p>|</p>
        <a class="filtro plataforma selecionado" id="all" href="#" @click="alerta()">Todos</a>
      </div>
      <div class="fav">
        <a id="favoritos" class="textt" href="#" @click="alerta()">Favoritos</a>

      </div>
    </div>
  </nav>
</template>
<script setup>
function alerta() {
  alert('Função em desenvolvimento')
}
</script>
