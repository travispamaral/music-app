<template>
  <aside
    :class="[{ 'is-collapsed': isCollapsed }, { 'is-open': isOpen }]"
    @mouseenter="handleMouseEnter"
    @mouseleave="handleMouseLeave"
  >
    <div class="logo">
      Groovvy
    </div>
    <nav
      v-for="(section, i) in menu"
      :key="i"
      class="fa-ul"
    >
      <li class="title">
        {{ section.title }}
      </li>
      <li
        v-for="(item, idx) in section.items"
        :key="idx"
        :class="{ 'active': i === 0 && idx === 0 }"
      >
        <a :href="item.url">
          <span class="fa-li">
            <i
              class="fa"
              :class="item.icon"
            />
          </span>
          {{ item.name }}
        </a>
      </li>
    </nav>
  </aside>
</template>

<script>
import menu from './menu'

const WINDOW_WIDTH = 900

export default {
  name: 'Sidebar',
  data () {
    return {
      menu,
      isOpen: false,
      windowWidth: window.innerWidth
    }
  },
  computed: {
    isCollapsed () {
      return this.windowWidth <= WINDOW_WIDTH
    }
  },
  mounted () {
    window.onresize = () => {
      this.windowWidth = window.innerWidth
    }
  },
  beforeDestroy () {
    window.onresize = null
  },
  methods: {
    handleMouseEnter () {
      if (this.isCollapsed && !this.isOpen) {
        this.isOpen = true
      }
    },
    handleMouseLeave () {
      if (this.isCollapsed && this.isOpen) {
        this.isOpen = false
      }
    }
  }
}
</script>

<style lang="scss" scoped>
$breakpoint: 900px;
aside {
  position: fixed;
  top: 0;
  bottom: 0;
  width: calc(var(--sidebarWidth) - 2rem);
  padding-left: 2rem;
  background-color: var(--gry);
  overflow: hidden;
  transition: width 300ms cubic-bezier(.215, .61, .355, 1);
  z-index: 1;
  .logo {
    display: flex;
    align-items: center;
    height: var(--headerHeight);
    margin-bottom: 3rem;
  }
  nav {
    list-style-type: none;
    margin: 0 0 3rem;
    padding: 0;
    li {
      &.title {
        text-transform: uppercase;
        color: var(--textLite);
        font-weight: 500;
      }
      &.active { border-right: 2px solid var(--accent); }
      a {
        display: block;
        text-decoration: none;
        color: var(--textDrk);
      }
      &:not(:last-of-type) { margin-bottom: 1.25rem; }
    }
  }

  &.is-collapsed {
    width: 0;
    &.is-open {
      width: calc(var(--sidebarWidth) - 2rem);
    }
  }
}
</style>
