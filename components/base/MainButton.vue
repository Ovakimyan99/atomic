<template>
  <button class="main-button" :class="{light: revert}">
    <slot />
  </button>
</template>

<script>
export default {
  name: 'MainButton',
  props: {
    revert: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
.main-button {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: transparent;
  width: fit-content;
  padding: 15px 30px;
  border-radius: 50px;
  position: relative;
  overflow: hidden;
  transition: 0.4s ease;
  color: $font-color;
  border: 1px solid $font-color;
  cursor: pointer;

  &.light {
    color: $background-color;
    border-color: $background-color;

    &:hover {
      background-color: $background-color;
      color: $font-color;
      border-color: $font-color;
    }
  }

  &:hover {
    background-color: $font-color;
    color: $background-color;
    border-color: $background-color;
  }

  &__content {
    display: flex;
    align-items: center;
    gap: 1rem;
    height: inherit;
    justify-content: space-between;
    width: 100%;
    line-height: 1;
    font-size: 15px;
    align-items: center;

    @media (min-width: 600px) {
      font-size: 18px;
    }

    &-icon {
      margin-left: 13px;
    }
  }
}
</style>
