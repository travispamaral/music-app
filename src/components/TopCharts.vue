<template>
  <div class="top-charts">
    <Card>
      <template #title>
        Genres
      </template>
      <template #action>
        See all
      </template>
      <div class="chart-wrapper">
        <div
          v-for="(artist, idx) in artists"
          :key="idx"
          class="artist"
        >
          <div class="index">
            0{{ idx }}
          </div>
          <div class="img">
            <img :src="`https://source.unsplash.com/random/120x120?sig=${i}`">
          </div>
          <div class="details">
            <span>{{ artist.song }}</span>
            <span>{{ artist.name }}</span>
          </div>
          <div class="time">
            <strong>3:45</strong>
          </div>
          <div class="play">
            <button class="button button-outline">
              <PlayIcon />
            </button>
          </div>
        </div>
      </div>
    </Card>
  </div>
</template>

<script>
import Card from '@/components/Card'
import PlayIcon from '../../public/img/icons/playBtn.svg'

export default {
  name: 'TopCharts',
  components: { Card, PlayIcon },
  data () {
    return {
      artists: [
        { song: 'Havana', name: 'Camilla Cabello' },
        { song: 'Jesus Is King', name: 'Kanye West' },
        { song: 'Closer', name: 'The Chain Smokers' },
        { song: 'Lean On', name: 'Major Lazer ft DJ Snake' }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.top-charts {
  grid-column: 3 / 6;
  grid-row: 2 / -1;
  .chart-wrapper {
    display: flex;
    flex-direction: column;
    .artist {
      display: grid;
      grid-template-columns: 1fr 1fr 5fr 1fr 1fr;
      grid-gap: 1rem;
      align-items: center;
      &:not(:last-of-type) { margin-bottom: 1rem; }
      .index {
        text-align: center;
        color: var(--gryDrk);
      }
      img {
        max-width: 60px;
        border-radius: 4px;
      }
      .details span {
        display: block;
        &:first-of-type { font-weight: bold; }
        &:last-of-type { color: var(--gryDrk); }
      }
      .play button {
        border-radius: 4px;
        padding: .25rem;
        svg {
          width: 10px;
          height: 10px;
        }
      }
    }
  }
}
</style>
