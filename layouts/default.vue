<template>
  <div class="layout">
    <AppHeader />
    <main>
      <Nuxt keep-alive />
    </main>
    <AppFooter>
      <AppSquareScreen>
        <template #IntegralPart>
          <h3 class="footer-title">
            <span class="footer-title__ask">Задайте вопрос,</span>
            <span class="text-gradient">мы ответим быстро</span>
          </h3>

          <AppButton class="footer-btn" :revert="true">
            Наша презентация
          </AppButton>

          <!-- Social Icons & Address -->
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
import AppButton from '@/components/base/MainButton.vue'
import AppFooterCookies from '@/components/basePage/FooterCookies'
import AppFooter from '@/components/basePage/Footer'
import AppHeader from '@/components/basePage/Header'
import AppSquareScreen from '@/components/base/SquareScreen.vue'
import AppSquareInfo from '@/components/base/SquareInfo.vue'
import AppAddress from '@/components/base/Address'

export default {
  name: 'DefaultLayout',
  components: {
    AppButton,
    AppFooterCookies,
    AppFooter,
    AppHeader,
    AppSquareScreen,
    AppSquareInfo,
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
.footer {
  &-title {
    font-size: 30px;
    line-height: 1;
    margin: 0;
    font-weight: 400;

    @media (min-width: 680px) {
      font-size: 40px;
    }
    @media (min-width: 980px) {
      font-size: 50px;
    }

    @media (min-width: 1100px) {
      font-size: 60px;
    }

    &__ask {
      display: block;
    }
  }

  &-btn {
    margin: 60px 0 50px;

    @media (min-width: 687px) {
      margin: 80px 0 50px;
    }

    @media (min-width: 1100px) {
      margin: 0;
      margin-bottom: 20px;
    }
  }
}
</style>
