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
  transition:  background 0.5s ease;
  position: relative;
  border: $border-in-light;
  border-bottom: none;
  border-left: none;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: calc(25% - 4rem);
  flex-grow: 1;
  flex-basis: 100%;
  min-height: calc(50vh - 4rem);
  background: $font-color;
  color: $background-color;

  ::v-deep .border {
    border-left: $border-in-light;
  }

  @media (min-width: 580px) {
    height: auto;
    flex-basis: calc(50% - 5rem);
  }

  &__text {
    line-height: 1.1;
    color: $background-color;
    z-index: 2;
    position: relative;

    font-size: 15px;
    letter-spacing: -0.025em;
    max-width: 155px;
  }

  &__title {
    font-size: 24px;
    line-height: 1.1;
    z-index: 2;
    position: relative;
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
