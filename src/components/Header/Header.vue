<template>
  <header>
    <nav>
      <li>
        <a
          href="#"
          class="active"
        >Music</a>
      </li>
      <li><a href="#">Podcast</a></li>
      <li><a href="#">Live</a></li>
    </nav>
    <SearchBar />
    <div class="profile">
      <NotificationIcon has-notifications />
      <SettingsIcon />
      <User />
    </div>
  </header>
</template>

<script>
import User from './User'
import NotificationIcon from './NotificationIcon'
import SettingsIcon from '../../../public/img/icons/settings.svg'
import SearchBar from './SearchBar'

export default {
  name: 'Header',
  components: { NotificationIcon, SettingsIcon, User, SearchBar }
}
</script>

<style lang="scss">
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: var(--headerHeight);
  nav {
    display: flex;
    justify-content: space-between;
    list-style: none;
    li  {
      &:not(:first-of-type) { margin-left: .5rem; }
      &:not(:last-of-type) { margin-right: .5rem; }
      a {
        position: relative;
        text-decoration: none;
        text-transform: uppercase;
        color: var(--gryDrk);
        &.active { color: var(--accent); }
      }
    }
  }
  .profile {
    display: flex;
    justify-content: space-between;
    align-items: center;
    svg {
      margin-right: 1rem;
      path { fill: var(--gryDrk); }
    }
  }
}
</style>
