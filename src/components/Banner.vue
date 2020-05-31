<template>
  <div
    v-if="!bannerHidden"
    class="banner"
  >
    <p>This design was from Dibbble user <a href="https://dribbble.com/ema_ike">Emmanuel Ikechukwu</a>, the design can be found <a href="https://dribbble.com/shots/11019630-Music-Player-Web-Application/attachments/2613913?mode=media">here</a>.</p>
    <p>The goal of this exercise was to create a web prototype as accurate to the design as possible with no specs or design files. Future plans include connecting it to a third party music api like Spotify.</p>
    <button
      class="button-primary"
      @click="closeBanner"
    >
      CLOSE
    </button>
  </div>
</template>

<script>
export default {
  name: 'Banner',
  data () {
    return {
      bannerHidden: false
    }
  },
  mounted () {
    this.bannerHidden = localStorage.getItem('hideBanner') || false
  },
  methods: {
    closeBanner () {
      this.bannerHidden = true
      localStorage.setItem('hideBanner', true)
    }
  }
}
</script>

<style lang="scss" scoped>
.banner {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: #fff;
  padding: 1rem;
  text-align: center;
  z-index: 100;
  box-shadow: 0 5px 20px rgba(0,0,0,.05);
  a { color: var(--accent); }
  button { border-radius: 4px; }
}
</style>
