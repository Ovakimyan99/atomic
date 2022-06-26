<template>
  <section class="other-footer dark">
    Продолжая использовать наш сайт, вы даете согласие на обработку файлов cookie. ©ATOMIC, 2022
  </section>
</template>

<script>
export default {
  name: 'FooterCookies'
}
</script>

<style lang="scss" scoped>
.other-footer {
  padding: 25px 20px;
  text-align: center;
  background-color: $background-color;
  border-top: 1px solid rgba(163, 163, 163, 0.3);

  @media (min-width: 1180px) {
    padding: 25px $margin-default;
  }
}
</style>
