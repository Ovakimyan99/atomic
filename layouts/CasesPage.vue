<template>
  <div>
    <AppHeader />
    <main>
      <nuxt />
    </main>
    <AppFooterCookies />
  </div>
</template>

<script>
import AppFooterCookies from '@/components/basePage/AppFooterCookies'
import AppHeader from '@/components/basePage/Header'

export default {
  name: 'LayoutCasesPage',
  components: [
    AppFooterCookies,
    AppHeader
  ]
}
</script>
