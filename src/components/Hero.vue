<template>
  <div class="hero">
    <div class="hero-title">
      Trending New Hits
    </div>
    <div class="artist">
      <div class="title">
        The Havanna
      </div>
      <div class="subtitle">
        <span>Camila Cabello</span>
        <span>63Million Plays</span>
      </div>
      <div class="actions">
        <button class="button-primary">
          Listen Now
        </button>
        <button class="button-outline">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
            width="20px"
            height="20px"
          >
            <path
              fill="#000"
              d="M10 3.22l-.61-.6a5.5 5.5 0 00-7.78 7.77L10 18.78l8.39-8.4a5.5 5.5 0 00-7.78-7.77l-.61.61z"
            />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Hero'
}
</script>

<style lang="scss" scoped>
.hero {
  color: var(--textDrk);
  font-weight: 600;
  .hero-title {
    display: inline;
  }
  .artist {
    margin: 4rem 0;
    .title {
      font-size: 6rem;
      margin-bottom: 1rem;
    }
    .subtitle {
      font-size: 1.25rem;
      margin-bottom: 2rem;
      span:first-of-type {
        margin-right: 1rem;
      }
      span:last-of-type {
        font-weight: 400;
        color: var(--gryDrk)
      }
    }
    .actions {
      display: flex;
      align-items: center;
      button:first-of-type {
        margin-right: 1rem;
      }
    }
  }
}
</style>
