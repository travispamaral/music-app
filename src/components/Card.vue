<template>
  <div
    :class="{ 'dark': isDark }"
    class="card"
  >
    <div class="card-header">
      <div class="card-title">
        <slot name="title" />
      </div>
      <div class="card-action">
        <slot name="action" />
      </div>
    </div>
    <div class="card-body">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    isDark: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
.card {
  box-sizing: border-box;
  height: 100%;
  padding: 1.5rem;
  border-radius: 4px;
  background-color: var(--white);
  &.dark {
    background-color: var(--blk);
    color: var(--white);
  }
  .card-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 2rem;
    .card-title {
      font-weight: bold;
    }
    .card-action {
      color: var(--gryDrk);
    }
  }
}
</style>
