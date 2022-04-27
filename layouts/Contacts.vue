<template>
  <div class="layout">
    <AppHeader />
    <main>
      <Nuxt keep-alive />
    </main>
    <AppFooter>
      <AppSquareScreen>
        <template #IntegralPart>
          <a class="contact-tel" href="tel:+74951504002">+7 495 150 40 02</a>
          <AppAddress />
        </template>
        <template #CrushedParts>
          <AppSquareInfo
            v-for="{ title } of squareInfo"
            :key="title"
          >
            <template #title>
              {{ title }}
            </template>
          </AppSquareInfo>
        </template>
      </AppSquareScreen>
    </AppFooter>
    <AppFooterCookies />
  </div>
</template>

<script>
import AppHeader from '@/components/basePage/Header'
import AppFooter from '@/components/basePage/Footer'
import AppSquareInfo from '@/components/base/SquareInfo.vue'
import AppSquareScreen from '@/components/base/SquareScreen.vue'
import AppFooterCookies from '@/components/basePage/FooterCookies'
import AppAddress from '@/components/base/Address'

export default {
  name: 'LayoutCasesPage',
  components: {
    AppHeader,
    AppFooter,
    AppSquareScreen,
    AppSquareInfo,
    AppFooterCookies,
    AppAddress
  },
  data() {
    return {
      squareInfo: [
        {
          title: 'Позвоните'
        },
        {
          title: 'Напишите'
        },
        {
          title: 'Запишитесь на констультацию'
        },
        {
          title: 'Приходите к нам'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.contact-tel {
  text-decoration: none;
  color: $background-color;
  font-size: 30px;
  margin-bottom: 60px;
}
</style>
