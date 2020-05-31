<template>
  <div class="player">
    <Card is-dark>
      <template #title>
        Top Artists
      </template>
      <template #action>
        <PlaylistIcon />
      </template>
      <div class="player-content">
        <div class="currently-playing">
          <img :src="`https://source.unsplash.com/random/160x160`">
          <h2 class="mb-0">
            Butterfly Effect
          </h2>
          <h4 class="my-2">
            Travis Scott
          </h4>
          <small>Best of 2020</small>
        </div>
        <div class="controls">
          <RepeatIcon />
          <RewindIcon />
          <button>
            <PlayIcon />
          </button>
          <ForwardIcon />
          <ShuffleIcon />
          <div class="lyrics">
            <Chevron />
            <span>Lyrics</span>
          </div>
        </div>
      </div>
    </Card>
  </div>
</template>

<script>
import Card from '@/components/Card'
import PlaylistIcon from '../../public/img/icons/playlist.svg'
import RewindIcon from '../../public/img/icons/rewind.svg'
import ForwardIcon from '../../public/img/icons/forward.svg'
import PlayIcon from '../../public/img/icons/playBtn.svg'
import RepeatIcon from '../../public/img/icons/repeat.svg'
import ShuffleIcon from '../../public/img/icons/shuffle.svg'
import Chevron from '../../public/img/icons/chevron-up.svg'

export default {
  name: 'Player',
  components: {
    Card,
    PlaylistIcon,
    RewindIcon,
    ForwardIcon,
    PlayIcon,
    RepeatIcon,
    ShuffleIcon,
    Chevron
  }
}
</script>

<style lang="scss">
.player .card {
  display: grid;
  grid-template-rows: auto 1fr;
  .card-body {
    display: grid;
    grid-template-rows: repeat(3, 1fr);
  }
}
</style>

<style lang="scss" scoped>
.player {
  grid-column: 6 / -1;
  grid-row: 1 / -1;
  svg path { fill: var(--white); }
  .player-content {
    display: grid;
    grid-row: 1 / -1;
    .currently-playing {
      display: flex;
      flex-direction: column;;
      align-items: center;
      justify-content: center;
      grid-row: 1 / 3;
      img { border-radius: 4px; }
      small { color: var(--gryDrk); }
    }
    .controls {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: space-around;
      margin: 0 -1.5rem -1.5rem;
      padding: 2rem;
      border-radius: 0 0 4px 4px;
      background-color: var(--accent);
      button {
        background: var(--white);
        border-radius: 1rem;
        svg path { fill: var(--accent); }
      }
      svg {
        width: 1rem;
        height: 1rem;
        path { fill: var(--white); }
      }
      .lyrics {
        position: absolute;
        bottom: 0.5rem;
        display: flex;
        flex-direction: column;
        width: 100%;
        text-transform: uppercase;
        text-align: center;
        svg {
          margin: 0 auto;
          path { fill: var(--white); }
        }
      }
    }
  }
}
</style>
