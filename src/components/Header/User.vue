<template>
  <div class="user">
    <img src="@/assets/profile.jpeg">
    <span>{{ username }}</span>
  </div>
</template>

<script>
export default {
  name: 'User',
  props: {
    username: {
      type: String,
      default: 'Travis Amaral'
    }
  }

}
</script>

<style lang="scss" scoped>
.user {
  display: flex;
  align-items: center;
  white-space:nowrap;
  padding: .5rem;
  border-radius: 4px;
  color: var(--white);
  background-color: var(--blk);
  img {
    width: 1.5rem;
    border-radius: 2px;
    margin-right: .5rem;
  }
  span {
    max-width: 10ch;
    overflow: hidden;
    text-overflow: ellipsis
  }
}
</style>
