<template>
  <div class="square-info">
    <h2 class="square-info__title">
      <slot name="title" />
    </h2>
    <p class="square-info__text">
      <slot name="content" />
    </p>
  </div>
</template>

<script>
export default {
  name: 'SquareInfo',
  computed: {
    slot () {
      return !!this.$slots.title || !!this.$slots.content
    }
  }
}
</script>

<style lang="scss" scoped>
.square-info {
  transition: all 0.5s;
  border: $border-in-light;
  border-bottom: none;
  border-left: none;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: 100%;
  flex-grow: 1;
  flex-basis: 100%;
  min-height: 25vh;

  ::v-deep .border {
    border-left: $border-in-light;
  }

  @media (min-width: 580px) {
    height: 50%;
    flex-basis: 50%;
  }

  &__text {
    font-size: 24px;
    line-height: 26px;
    letter-spacing: -0.05em;
    color: $background-color;
  }

  &:hover &__text, &__icon {
    color: $font-color;
  }

  &:hover {
    background-color: $background-color;
    color: $font-color;
    cursor: pointer;

    .menu__icon {
      color: $font-color;
    }
  }
}
</style>
