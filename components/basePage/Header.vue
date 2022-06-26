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
      <AppSquareScreen v-show="hiddenMenu" class="menu">
        <template #IntegralPart>
          <div class="menu-navigation">
            <nuxt-link
              v-for="{name, link} of routs"
              :key="name"
              :to="link"
              exact-active-class="active-rout"
              class="menu-navigation__text"
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
  height: calc(100% - 61px);
  background-color: $font-color;
  display: flex;
  flex-direction: column;
  overflow-y: auto;

  @media (min-width: 980px) {
    flex-direction: row;
    overflow-y: hidden;
  }

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

  &-navigation {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100%;

    @media (min-width: 480px) {
      flex-direction: row;
      justify-content: space-between;
      overflow-x: auto;
      height: auto;
    }

    @media (min-width: 678px) {
      margin: auto;
      margin-left: 0;
      flex-direction: column;
      justify-content: center;
      overflow: hidden;
    }

    &__text {
      transition: all 0.5s;
      font-weight: 300;
      font-size: 43px;
      color: $background-color;
      text-decoration: none;
      line-height: 1.1;
      display: inline-block;
      width: max-content;

      &:hover {
        cursor: pointer;
        @include textGradient;
      }

      @media (min-width: 480px) {
        font-size: 25px;
        flex: 1 0 auto;

        &:not(:last-child) {
          margin-right: 20px;
        }
      }

      @media (min-width: 678px) {
        font-size: 60px;
        flex: auto;
      }

      @media (min-width: 980px) {
        font-size: 68px;
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
