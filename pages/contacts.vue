<template>
  <section class="contacts">
    <AppPageTitle class="contacts__title text-gradient">
      Контакты
    </AppPageTitle>
  </section>
</template>

<script>
import AppPageTitle from '@/components/basePage/PageTitle.vue'

export default {
  name: 'ContactsPage',
  components: {
    AppPageTitle
  }
}
</script>

<style lang="scss" scoped>
.contacts {
  overflow: hidden;

  @media (min-width: 900px) {
    min-height: 60vh;
  }

  &__title {
    margin: 162px 26px 72px;

    @media (min-width: 768px) {
      padding: 50px 0 64px 0px;
    }

    @media (min-width: 980px) {
      padding: 0 0 0 40px;
    }
  }
}
</style>
