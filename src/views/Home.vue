<template>
  <div>
    <Hero />
    <div class="home-grid">
      <TopArtists />
      <Player />
      <Genres />
      <TopCharts />
    </div>
  </div>
</template>

<script>
import Hero from '@/components/Hero'
import TopArtists from '@/components/TopArtists'
import Player from '@/components/Player'
import Genres from '@/components/Genres'
import TopCharts from '@/components/TopCharts'

export default {
  name: 'Home',
  components: {
    Hero,
    TopArtists,
    Player,
    Genres,
    TopCharts
  },
  data () {
    return {
      playlists: [
        {
          title: 'Daily Mix',
          description: 'Lane 8, David August, HVOB & More'
        },
        {
          title: 'Tosch Remixes',
          description: 'Andhim'
        },
        {
          title: 'Infinity',
          description: 'Scarlxrd'
        },
        {
          title: 'Get Home Happy',
          description: 'Favorite Songs'
        },
        {
          title: 'Daily Mix',
          description: 'Lane 8, David August, HVOB & More'
        },
        {
          title: 'Tosch Remixes',
          description: 'Andhim'
        },
        {
          title: 'Infinity',
          description: 'Scarlxrd'
        },
        {
          title: 'Get Home Happy',
          description: 'Favorite Songs'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.home-grid {
  display: grid;
  grid-gap: 1.5rem;
  grid-template-columns: repeat(7, 1fr);
  grid-template-rows: .5fr 1fr;
}
</style>
