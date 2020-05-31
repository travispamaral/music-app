<template>
  <div class="genres">
    <Card>
      <template #title>
        Genres
      </template>
      <template #action>
        See all
      </template>
      <div class="genre-wrapper">
        <div
          v-for="(g, idx) in genres"
          :key="idx"
          :style="{backgroundColor: colors[idx]}"
          class="genre"
        >
          {{ g }}
        </div>
      </div>
    </Card>
  </div>
</template>

<script>
import Card from '@/components/Card'

export default {
  name: 'Genres',
  components: { Card },
  data () {
    return {
      genres: ['Dance Beat', 'Electo Pop', 'Alternative Indie', 'Hip Hop', 'Classical', 'Rap'],
      colors: ['#DCE7F2', '#FEFAF2', '#FDF1EC', '#E7EEEE', '#FEF8FC', '#F1EFFE']
    }
  }
}
</script>

<style lang="scss" scoped>
.genres {
  grid-column: 1 / 3;
  grid-row: 2 / -1;
  .genre-wrapper {
    display: flex;
    flex-wrap: wrap;
    .genre {
      margin: 0 1rem 1rem 0;
      padding: 1.5rem;
      border-radius: 4px;
    }
  }
}
</style>
