<template>
  <NavBar />
  <SearchBar />
  <main>
    <GameCard
      v-for="game in games"
      :key="game.id"
      :title="game.title"
      :link="game.link"
      :imgSrc="game.img"
    />  
  </main>
  <Footer />
</template>

<script setup>
import NavBar from '@/components/NavBar.vue'
import SearchBar from '@/components/SearchBar.vue'
import GameCard from '@/components/GameCard.vue'
import Footer from '@/components/Footer.vue'

const games = [
  { id: 1, title: 'Counter Strike 1.6', link: 'https://play-cs.com/pt/', img: '/imgs/CS1.6.png' },
  { id: 2, title: 'King of Fighters', link: 'https://jogosnainternet.com.br/jogo/the-king-of-the-fighter-2002/', img: '/imgs/KOF.png' },
  { id: 3, title: 'Minecraft', link: 'https://eaglercraft.com/', img: '/imgs/Minecraft.jpg' },
  { id: 4, title: 'Pokemon Showdown', link: 'https://pokemonshowdown.com/', img: '/imgs/Pokemon.avif' },
  { id: 5, title: 'Naruto Vs Bleach', link: 'https://jogosnainternet.com.br/jogo/bleach-vs-naruto-30/', img: '/imgs/NarutovsBleach.jpg' },
  { id: 6, title: 'Venge.io', link: 'https://venge.io/', img: '/imgs/Venge.jpg' },
  { id: 7, title: 'Supremacy 1914', link: 'https://www.supremacy1914.com/?source=homescreen', img: '/imgs/Supremacy.jpg' },
  { id: 8, title: 'Super Mario World', link: 'https://jogosnainternet.com.br/jogo/super-mario-world/', img: '/imgs/SuperMario.jfif' },
  { id: 9, title: 'Street Fighter II', link: 'https://www.retrogames.cz/play_304-SNES.php', img: '/imgs/lUTA.jfif' },
  { id: 10, title: 'Subway Surfers', link: 'https://subway-surfers.org/', img: '/imgs/SubwaySurfers.jfif' },
  { id: 11, title: 'Marvel Vs Capcom', link: 'https://jogosnainternet.com.br/jogo/marvel-vs-capcom/', img: '/imgs/marvelvscapcom.jpg' },
  { id: 12, title: 'Make it Meme', link: 'https://makeitmeme.com/pt/', img: '/imgs/Makeitmeme.jfif' },
  { id: 13, title: 'HaxBall', link: 'https://www.haxball.com/', img: '/imgs/haxball.jpg' },
  { id: 14, title: 'Poxel.io', link: 'https://poxel.io/', img: '/imgs/poxel.io.png' },
  { id: 15, title: 'Tower Defense', link: 'https://now.gg/apps/inlogic/51193/tower-defense.html', img: '/imgs/tower.png' },
  { id: 16, title: 'Punch Hero', link: 'https://now.gg/apps/spatial-io/51691/punch-hero.html', img: '/imgs/punch.png' },
  { id: 15, title: 'Stumble Guys', link: 'https://www.stumbleguys.com/pt-BR/play', img: '/imgs/Stumble.jpg' }
]
</script>
