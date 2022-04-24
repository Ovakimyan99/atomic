<template>
  <div class="layout">
    <AppHeader />
    <main>
      <Nuxt keep-alive />
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
  name: 'DefaultLayout',
  components: {
    AppFooterCookies,
    Footer,
    AppHeader
  }
}
</script>
