<template>
  <section class="section-wrapper">
    <div class="section-integral-path section-integral">
      <slot name="IntegralPart" />
    </div>
    <div class="section-integral-path section-crushed">
      <slot name="CrushedParts" />
    </div>
  </section>
</template>

<style scoped lang="scss">
.section {
  &-wrapper {
    display: flex;
    flex-direction: column-reverse;
    border: 1px solid $unimportant;
    border-right: none;
    border-left: none;

    &.revert {
      flex-direction: column;
    }

    @media (min-width: 980px) {
      flex-direction: row;

      &.revert {
        flex-direction: row;
      }
    }
  }

  &-integral, &-crushed {
    &-path {
      flex: 1 0 50%;
    }
  }

  &-crushed {
  }
}
</style>
