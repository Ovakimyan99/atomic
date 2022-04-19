<template>
  <div>
    <AppHeader />
    <main>
      <Nuxt />
    </main>
    <AppFooter />
    <AppFooterCookies />
  </div>
</template>

<script>
import AppFooterCookies from '@/components/basePage/AppFooterCookies'
import AppFooter from '@/components/basePage/AppFooter'
import AppHeader from '@/components/basePage/Header'

export default {
  name: 'DefaultLayout',
  components: [
    AppFooterCookies,
    AppFooter,
    AppHeader
  ]
}
</script>
