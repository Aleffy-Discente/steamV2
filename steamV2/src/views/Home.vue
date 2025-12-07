<template>
  <NavBar />
  <SearchBar v-model="query" />
  <main>
    <GameCard
      v-for="game in filteredGames"
      :key="game.id"
      :title="game.title"
      :link="game.link"
      :imgSrc="game.img"
    />
  </main>
  <Footer />
</template>

<script setup>
import { ref, computed, onMounted } from 'vue'
import NavBar from '@/components/NavBar.vue'
import SearchBar from '@/components/SearchBar.vue'
import GameCard from '@/components/GameCard.vue'
import Footer from '@/components/Footer.vue'

onMounted(() => { document.title = 'GameHub 🎮' })

const query = ref('')

const games = ref([
  { id: 1,  title: 'Counter Strike 1.6', link: 'https://play-cs.com/pt/', img: '/steamV2/imgs/CS1.6.png' },
  { id: 2,  title: 'King of Fighters', link: 'https://jogosnainternet.com.br/jogo/the-king-of-the-fighter-2002/', img: '/steamV2/imgs/KOF.png' },
  { id: 3,  title: 'Minecraft', link: 'https://eaglercraft.com/', img: '/steamV2/imgs/Minecraft.jpg' },
  { id: 4,  title: 'Pokémon Showdown', link: 'https://pokemonshowdown.com/', img: '/steamV2/imgs/Pokemon.avif' },
  { id: 5,  title: 'Naruto Vs Bleach', link: 'https://jogosnainternet.com.br/jogo/bleach-vs-naruto-30/', img: '/steamV2/imgs/NarutovsBleach.jpg' },
  { id: 6,  title: 'Venge.io', link: 'https://venge.io/', img: '/steamV2/imgs/Venge.jpg' },
  { id: 7,  title: 'Supremacy 1914', link: 'https://www.supremacy1914.com/?source=homescreen', img: '/steamV2/imgs/Supremacy.jpg' },
  { id: 8,  title: 'Super Mario World', link: 'https://jogosnainternet.com.br/jogo/super-mario-world/', img: '/steamV2/imgs/SuperMario.jfif' },
  { id: 9,  title: 'Street Fighter II', link: 'https://www.retrogames.cz/play_304-SNES.php', img: '/steamV2/imgs/lUTA.jfif' },
  { id: 10, title: 'Subway Surfers', link: 'https://subway-surfers.org/', img: '/steamV2/imgs/SubwaySurfers.jfif' },
  { id: 11, title: 'Marvel Vs Capcom', link: 'https://jogosnainternet.com.br/jogo/marvel-vs-capcom/', img: '/steamV2/imgs/marvelvscapcom.jpg' },
  { id: 12, title: 'Make it Meme', link: 'https://makeitmeme.com/pt/', img: '/steamV2/imgs/Makeitmeme.jfif' },
  { id: 13, title: 'HaxBall', link: 'https://www.haxball.com/', img: '/steamV2/imgs/haxball.jpg' },
  { id: 14, title: 'Poxel.io', link: 'https://poxel.io/', img: '/steamV2/imgs/poxel.io.png' },
  { id: 15, title: 'Tower Defense', link: 'https://now.gg/apps/inlogic/51193/tower-defense.html', img: '/steamV2/imgs/tower.png' },
  { id: 16, title: 'Punch Hero', link: 'https://now.gg/apps/spatial-io/51691/punch-hero.html', img: '/steamV2/imgs/punch.png' },
  { id: 17, title: 'Stumble Guys', link: 'https://www.stumbleguys.com/pt-BR/play', img: '/steamV2/imgs/Stumble.jpg' },
  { id: 18, title: 'Timeguessr', link: 'https://timeguessr.com/', img: '/steamV2/imgs/time.png' },
  { id: 19, title: 'level devil', link: 'https://leveldevil.vip/', img: '/steamV2/imgs/level.jpeg' },
  { id: 20, title: 'Hole io', link: 'https://holeio.com/', img: '/steamV2/imgs/hole.jpeg' },
  { id: 21, title: 'Chess', link: 'https://www.chess.com/pt-BR', img: '/steamV2/imgs/chess.webp' }, 
  { id: 22, title: '2048', link: 'https://2048game.com/', img: '/steamV2/imgs/2048.png' },
  { id: 23, title: 'Emupedia', link: 'https://emupedia.net/beta/emuos/', img: '/steamV2/imgs/emu.png' },
  { id: 24, title: 'Elvenar', link: 'https://br0.elvenar.com/web/glps', img: '/steamV2/imgs/elvenar.webp' },
  { id: 25, title: 'Forge of Empires', link: 'https://br-play.forgeofempires.com/', img: '/steamV2/imgs/forge.webp' },
  { id: 26, title: 'Death Shot', link: 'https://deadshot.io/', img: '/steamV2/imgs/deathShot.webp' },
  { id: 27, title: 'Overtide.io', link: 'https://overtide.io/', img: '/steamV2/imgs/overtide.png' },
  { id: 28, title: 'Hordes.io', link: 'https://hordes.io/', img: '/steamV2/imgs/hordes.webp' }
])

const clean = s => s.normalize('NFD').replace(/\p{Diacritic}/gu, '').toLowerCase()

const filteredGames = computed(() => {
  const q = clean(query.value.trim())
  if (!q) return games.value
  return games.value.filter(g => clean(g.title).includes(q))
})
</script>
