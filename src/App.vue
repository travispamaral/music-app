<template>
  <div id="app">
    <Banner />
    <Sidebar />
    <main>
      <Header />
      <section class="content">
        <router-view />
      </section>
    </main>
  </div>
</template>

<script>
import Sidebar from '@/components/Sidebar/Sidebar'
import Header from '@/components/Header/Header'
import Banner from '@/components/Banner'

export default {
  components: { Sidebar, Header, Banner }
}
</script>

<style lang="scss">
@import 'assets/styles/normalize.css';
@import 'assets/styles/utilities.scss';
$breakpoint: 900px;
:root {
  --gryDrk: #B3B6B9;
  --gryLite: #F6F7F7;
  --gry: #E9ECEF;
  --textDrk: #465062;
  --textLite: #9D9DA8;
  --blk: #25252C;
  --white: #FFFFFF;
  --accent: #5C76F7;

  --radius: 20px;
  --sidebarWidth: 200px;
  --headerHeight: 80px;
}

#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: var(--textDrk);

  main {
    margin-left: var(--sidebarWidth);
    padding: 0 2rem 2rem;
    min-height: 100vh;
    background-color: var(--gryLite);
    .content {
      margin-top: 3rem;
    }

    @media only screen and (max-width: $breakpoint) {
      margin-left: 20px;
    }
  }
}

button {
  display: inline-flex;
  align-items: center;
  padding: 1rem;
  color: var(--white);
  border: none;
  cursor: pointer;
  &.button-primary {
    border-radius: 50px;
    background-color: var(--accent);
  }
  &.button-outline {
    border: 2px solid var(--gryDrk);
    border-radius: 50%;
    svg path { fill: var(--accent); }
  }
}
</style>
