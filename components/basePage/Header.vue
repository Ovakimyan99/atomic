<template>
  <header class="header-wrapper">
    <nav class="header-menu">
      <nuxt-link class="header-image__wrapper" to="/">
        <img class="header-image" src="~/assets/img/base/main-logo.svg" alt="Atomic">
      </nuxt-link>
      <div class="header-burger" :class="{active: hiddenMenu}" @click="hiddenMenu = !hiddenMenu">
        <div class="header-burger-line header-burger--top" />
        <div class="header-burger-line header-burger--middle" />
        <div class="header-burger-line header-burger--bottom" />
      </div>
    </nav>
    <transition name="fade">
      <AppSquareScreen v-show="hiddenMenu" class="menu menu__content flex-rows">
        <template #IntegralPart>
          <div class="menu__navigation flex-columns">
            <nuxt-link
              v-for="{name, link} of routs"
              :key="name"
              :to="link"
              exact-active-class="active-rout"
              class="menu__navigation__text"
            >
              <span @click="hiddenMenu = false">
                {{ name }}
              </span>
            </nuxt-link>
          </div>
        </template>
        <template #CrushedParts>
          <div class="menu__about flex-row">
            <AppSquareInfo>
              <template #title>
                Позвоните
              </template>
            </AppSquareInfo>
            <AppSquareInfo>
              <template #title>
                Напишите
              </template>
            </AppSquareInfo>
            <AppSquareInfo>
              <template #title>
                Запишитесь на<br>констультацию
              </template>
            </AppSquareInfo>
            <AppSquareInfo>
              <template #title>
                Приходите<br>к нам
              </template>
            </AppSquareInfo>
          </div>
        </template>
      </AppSquareScreen>
    </transition>
  </header>
</template>

<script>
import AppSquareScreen from '~/components/base/SquareScreen'
import AppSquareInfo from '~/components/base/SquareInfo'

export default {
  name: 'AppHeader',
  components: {
    AppSquareInfo,
    AppSquareScreen
  },
  data() {
    return {
      hiddenMenu: false,
      routs: [
        {
          link: '/',
          name: 'Главная'
        },
        {
          link: '/aboutUs',
          name: 'О нас'
        },
        {
          link: '/cases',
          name: 'Кейсы'
        },
        {
          link: '/vacancies',
          name: 'Вакансии'
        },
        {
          link: '/contacts',
          name: 'Контакты'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
::-webkit-scrollbar {
  height: 1px !important;
}

.active-rout {
  @include textGradient;
  font-weight: 300;
}

.header {
  &-wrapper {
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    right: 0;
    z-index: 5;
  }

  &-menu {
    z-index: 4;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: $font-color;
    padding: 10px 20px;
    top: 0;
    left: 0;
    right: 0;
    background: $background-color;
    border-bottom: $border-in-dark;

    @media (min-width: 980px) {
      padding: 10px 60px;
    }
  }

  &-image {
    cursor: pointer;
    width: 100%;
    max-width: 137px;

    &__wrapper {
      max-height: 36px;
      display: inline-block;
      background-color: $background-color;
    }
  }

  &-burger {
    position: relative;
    width: 40px;
    height: 40px;
    flex: 0 0 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.3s ease;
    cursor: pointer;

    &-line {
      transition: transform 0.3s ease, background 0.3s ease, opacity 0.3s ease, top 0.3s ease;
      width: 35px;
      height: 4px;
      background: $font-color;
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      margin: auto;
    }

    &--top {
      top: -20px;
    }

    &--bottom {
      top: 20px;
    }

    &.active &--top {
      top: 0;
      transform: rotate(45deg);
    }

    &.active &--bottom {
      top: 0;
      transform: rotate(-45deg);
    }

    &.active &--middle {
      opacity: 0;
    }
  }
}

.menu {
  z-index: 2;
  position: fixed;
  width: 100%;
  height: calc(100% - 69px);
  background-color: $font-color;

  &__icon {
    cursor: pointer;
    position: absolute;
    right: 14px;
    top: 14px;
    background-color: $background-color;

    @media (min-width: 980px) {
      right: $margin-default;
      top: $margin-default;
    }
  }

  &__content {
    height: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    display: flex;
    flex-direction: column;

    @media (min-width: 800px) {
      flex-direction: row;
    }
  }

  &__navigation {
    width: calc(100% - 40px);
    height: auto;
    flex-grow: 0;
    display: flex;
    justify-content: center;
    flex-direction: column;
    border: none;
    padding: 0 20px;
    transform: translateY(25%);

    @media (min-width: 480px) {
      min-height: 36px;
      flex-direction: row;
      overflow-x: auto;
      overflow-y: hidden;
      justify-content: space-between;
    }

    @media (min-width: 678px) {
      padding: 80px 20px 40px;
      flex-direction: column;
      justify-content: center;
      overflow: visible;
    }

    @media (min-width: 800px) {
      width: calc(100% - 20px);
      padding: 0;
      padding-left: 20px;
      flex: 1 0 35%;
    }

    @media (min-width: 980px) {
      flex-direction: column;
      flex-grow: 1;
      // min-width: 25rem;
      // margin-left: $margin-default;
      padding-left: $margin-default;
    }

    &__text {
      transition: all 0.5s;
      font-weight: 300;
      font-size: 43px;
      color: $background-color;
      text-decoration: none;
      display: inline-block;
      width: max-content;
      line-height: 1.1;

      &:not(:last-child) {
        margin-bottom: 16px;

        @media (min-width: 480px) {
          margin-right: 32px;
          margin-bottom: 0;
        }

        @media (min-width: 678px) {
          margin-bottom: 16px;
        }
      }

      @media (min-width: 480px) {
        font-size: 25px;
        height: 36px;
        flex: 1 0 auto;
      }

      @media (min-width: 678px) {
        font-size: 60px;
        height: auto;
      }

      @media (min-width: 980px) {
        font-size: 68px;
      }

      &:hover {
        cursor: pointer;
        @include textGradient;
      }
    }
  }

  &__about {
    flex-basis: 45%;
    min-height: 100vh;
    flex-grow: 1;

    @media (min-width: 480px) {
      padding: 25px;
    }

    @media (min-width: 800px) {
      padding: 0;
    }
  }
}

.fade-enter-active {
  animation: fade-in 0.5s;
}

.fade-leave-active {
  animation: fade-in 0.5s reverse;
}

@keyframes fade-in {
  0% {
    transform: translateY(-50%);
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;
  }
}
</style>
