<template>
  <div class="social-wrapper">
    <nav class="social-links">
      <a href="#" class="social">
        <img src="@/assets/img/socials/instagram.png" class="social-img" alt="instagram">
      </a>
      <a href="#" class="social">
        <img src="@/assets/img/socials/facebook.svg" class="social-img" alt="facebook">
      </a>
      <a href="#" class="social">
        <img src="@/assets/img/socials/vk.svg" class="social-img" alt="vk">
      </a>
    </nav>
    <p class="address">
      Наш адрес: Москва, ул. Нижняя Сыромятническая, д.10 с.9 офис 326
    </p>
  </div>
</template>

<script>
export default {
  name: 'AppAddress'
}
</script>

<style scoped lang="scss">
.social {
  &:not(:last-child) {
    margin-right: 15px;
  }

  &-links {
    display: flex;
  }

  &-img {
    width: 25px;
    height: 25px;
  }
}

.address {
  margin-top: 20px;
  margin-bottom: 0;
  font-size: $font-size-small;
  line-height: 1;
}
</style>
