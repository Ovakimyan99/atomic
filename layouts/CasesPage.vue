<template>
  <div class="layout">
    <AppHeader />
    <main>
      <nuxt />
    </main>
    <AppFooterCookies />
  </div>
</template>

<script>
import AppFooterCookies from '@/components/basePage/FooterCookies'
import AppHeader from '@/components/basePage/Header'

export default {
  name: 'LayoutCasesPage',
  components: {
    AppFooterCookies,
    AppHeader
  }
}
</script>
