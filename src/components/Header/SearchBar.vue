<template>
  <div class="search">
    <SearchIcon />
    <input
      type="text"
      placeholder="Type to search"
    >
  </div>
</template>

<script>
import SearchIcon from '../../../public/img/icons/search.svg'
export default {
  name: 'SearchBar',
  components: { SearchIcon }
}
</script>

<style lang="scss" scoped>
.search {
  display: flex;
  align-items: center;
  padding: .5rem;
  border: 1px solid var(--gry);
  border-radius: 12px;
  svg {
    width: 20px;
    margin-right: .5rem;
    path { fill: var(--gryDrk); }
  }
  input {
    border: none;
    color: var(--gryDrk);
    background: none;
    &::placeholder {
      color: var(--gryDrk);
    }
    &:focus {
      outline: none;
    }
  }
}
</style>
