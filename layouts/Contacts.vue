<template>
  <div class="layout">
    <AppHeader />
    <main>
      <Nuxt />
    </main>
    <Footer />
    <AppFooterCookies />
  </div>
</template>

<script>
import AppFooterCookies from '@/components/basePage/FooterCookies'
import Footer from '@/components/basePage/Footer'
import AppHeader from '@/components/basePage/Header'

export default {
  name: 'LayoutCasesPage',
  components: {
    AppFooterCookies,
    Footer,
    AppHeader
  }
}
</script>
