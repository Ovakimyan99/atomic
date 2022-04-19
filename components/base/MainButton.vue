<template>
  <button class="main-button">
    <slot />
  </button>
</template>

<script>
export default {
  name: 'MainButton'
}
</script>

<style scoped lang="scss">
.main-button {

  &.revert {}
}
</style>
