<template>
  <h1 class="page-title">
    <slot />
  </h1>
</template>

<script>
export default {
  name: 'PageTitle'
}
</script>

<style lang="scss" scoped>
.page-title {
  line-height: 1.1;
  font-size: 39px;
  display: inline-block;
  width: max-content;
  font-family: $font-family;

  @media (min-width: 760px) {
    font-size: 45px;
  }

  @media (min-width: 1080px) {
    font-size: 60px;
  }
}
</style>
