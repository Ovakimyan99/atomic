<template>
  <section :class="{revers}" class="section-wrapper">
    <div :class="{revers}" class="section-integral-path section-integral">
      <slot name="IntegralPart" />
    </div>
    <div class="section-integral-path section-crushed">
      <slot name="CrushedParts" />
    </div>
  </section>
</template>

<script>
export default {
  name: 'AppSquareScreen',
  props: {
    revers: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
.section {
  &-wrapper {
    display: flex;
    flex-direction: column-reverse;
    border-bottom: $border-in-light;

    &.revert {
      flex-direction: column;
    }

    @media (min-width: 980px) {
      flex-direction: row;

      &.revert {
        flex-direction: row;
      }
    }

    &.revers {
      border-bottom: $border-in-dark;
    }
  }

  &-integral, &-crushed {
    &-path {
      background-color: $font-color;
      flex: 1 0 50%;
      color: $background-color;
    }
  }

  &-crushed {
    display: flex;
    flex-wrap: wrap;
  }

  &-integral {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    border: $border-in-light;
    border-left: none;
    border-bottom: none;

    padding: 40px 26px;
    width: calc(100% - 53px);
    flex-basis: calc(100% - 53px);

    @media (min-width: 480px) {
      flex: auto
    }

    @media (min-width: 678px) {
      flex: 1 0 50%;
    }

    @media (min-width: 980px) {
      flex-basis: calc(50% - 80px);
      padding: 40px;
    }

    @media (min-width: 1180px) {
      padding: $margin-default;
      width: calc(50% - $margin-default * 2);
      flex-basis: calc(50% - $margin-default * 2);
    }

    &.revers {
      background-color: $background-color;
      color: $font-color;
      border-right: $border-in-dark;
      border-top: $border-in-dark;
    }
  }
}
</style>
