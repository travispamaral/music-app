<template>
  <div class="top-artists">
    <Card>
      <template #title>
        Top Artists
      </template>
      <template #action>
        See all
      </template>
      <div class="artists">
        <div
          v-for="(artist, i) in artists"
          :key="i"
          class="artist"
        >
          <img
            :src="`https://source.unsplash.com/random/120x120?sig=${i}`"
          >
          <div>
            <p>{{ artist.name }}</p>
            <span>{{ artist.plays }}</span>
          </div>
        </div>
      </div>
    </Card>
  </div>
</template>

<script>
import Card from '@/components/Card'

export default {
  name: 'TopArtists',
  components: { Card },
  data () {
    return {
      artists: [
        {
          name: 'Travis Scott',
          img: '',
          plays: '44M'
        },
        {
          name: 'Billie Ellish',
          img: '',
          plays: '203M'
        },
        {
          name: 'This Kid',
          img: '',
          plays: '63M'
        },
        {
          name: 'Kanye',
          img: '',
          plays: '15M'
        },
        {
          name: 'Nicki Minaj',
          img: '',
          plays: '180M'
        },
        {
          name: 'Starboy',
          img: '',
          plays: '100M'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.top-artists {
  grid-column: 1 / 6;
  grid-row: 1 / 2;
  .artists {
    display: flex;
    justify-content: space-between;
    .artist {
      text-align: center;
      img {
        border-radius: .5rem;
        overflow: hidden;
        margin: 0 0 .5rem;
        width: 100%;
      }
      p {
        font-weight: bold;
        margin: 0;
      }
      span {
        display: block;
        color: var(--gryDrk);
      }
    }
  }
}
</style>
