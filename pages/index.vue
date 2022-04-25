<template>
  <div>
    <section class="directions-wrapper">
      <div class="directions__image-wrapper flex-column">
        <img class="directions__image" src="@/assets/img/main-page/directions.svg" alt="directions">
      </div>
      <div class="directions-services flex-column">
        <h2 class="directions-services__text">
          Мы реализуем
          <span class="text-gradient">омниканальные</span>
          проекты на стыке
          ecom, smm, modern
          trade & loyalty
          programs
        </h2>
      </div>
    </section>

    <section class="about-us flex-column">
      <h2 class="about-us__text">
        О нас в цифрах
      </h2>
      <div class="about-us__digits flex-row">
        <div class="about-us__digits-content">
          <h2 class="about-us__digits-content-title">
            +500
          </h2>
          <p class="about-us__digits-content-subtitle margin">
            реализованных проектов
          </p>
        </div>
        <div class="about-us__digits-content">
          <h2 class="about-us__digits-content-title">
            +15
          </h2>
          <p class="about-us__digits-content-subtitle margin">
            лет в рекламной индустрии
          </p>
        </div>
      </div>
    </section>

    <section class="works">
      <h2 class="works-title">
        Кейсы
      </h2>
      <!-- <Swiper
        class="works-examples swiper-wrapper"
      >
        <SwiperSlide
          v-for="{ text }, index of slides"
          :key="index"
          class="works-slide swiper-slide"
        >
          <h2 class="works-slide__title">
            {{ text }}
          </h2>
          <AppButton class="works-slide__button">
            Посмотреть
          </AppButton>
        </SwiperSlide>
      </Swiper> -->

      <div class="swiper-container works-examples">
        <!-- Additional required wrapper -->
        <div class="swiper-wrapper">
          <div
            v-for="{ text }, index of slides"
            :key="index"
            class="works-slide swiper-slide"
          >
            <h2 class="works-slide__title">
              {{ text }}
            </h2>
            <AppButton class="works-slide__button">
              Посмотреть
            </AppButton>
          </div>
        </div>

        <!-- If we need scrollbar -->
        <!-- <div class="swiper-scrollbar" /> -->
      </div>
    </section>
  </div>
</template>

<script>
import Swiper, { Scrollbar } from 'swiper'
import AppButton from '@/components/base/MainButton.vue'

// Import Swiper styles
import 'swiper/swiper-bundle.css'

Swiper.use([Scrollbar])

export default {
  name: 'IndexPage',
  components: {
    AppButton
  },
  data() {
    return {
      slides: [
        {
          text: 'Pringles',
          href: 'red'
        },
        {
          text: 'Arc’teryx',
          href: 'red'
        },
        {
          text: 'Kinder',
          href: ''
        },
        {
          text: 'Pringles',
          href: 'red'
        },
        {
          text: 'Arc’teryx',
          href: 'red'
        },
        {
          text: 'Kinder',
          href: ''
        }
      ]
    }
  },
  mounted() {
    // eslint-disable-next-line no-new
    new Swiper('.swiper-container', {
      loop: false,
      slidesPerView: 3.2,
      autoHeight: true,
      breakpoints: {
        320: {
          slidesPerView: 1
        },
        760: {
          slidesPerView: 2.35
        },
        980: {
          slidesPerView: 3.35
        }
      }
    })
  }
}
</script>

<style lang="scss" scoped>
.directions {
  &-wrapper {
    display: flex;
    flex-wrap: wrap;
    height: auto;
    border: $border-in-dark;
    border-right: 0;
    border-left: 0;
    padding: 50px 20px;

    @media (min-width: 640px) {
      flex-wrap: nowrap;
      min-height: 100vh;
    }

    @media (min-width: 768px) {
      padding: 50px $margin-default;
    }
  }

  &__image {
    max-height: 90%;
    max-width: 90%;
    width: 100%;
    height: 100%;
    margin: auto;

    @media (min-width: 460px) {
      max-height: 80%;
      max-width: 80%;
    }

    @media (min-width: 640px) {
      max-height: 90%;
      max-width: 90%;
    }

    @media (min-width: 768px) {
      max-height: 100%;
      max-width: 100%;
    }

    @media (min-width: 1100px) {
      max-height: 500px;
      max-width: 500px;
    }

    &-wrapper {
      padding-left: 0;
      justify-content: center;
      flex-grow: 1;
      flex-basis: 40%;

      @media (min-width: 640px) {
        flex: 1 0 50%;
      }

      @media (min-width: 768px) {
        flex: 1 0 45%;
        margin-right: 5%;
      }

      @media (min-width: 1100px) {
        padding-left: $margin-default;
        margin: 0;
        flex-basis: calc(50% - $margin-default);
      }
    }
  }

  &-services {
    justify-content: center;
    flex-grow: 1;
    flex-basis: 100%;
    margin-left: 0;
    width: auto;
    display: inline-flex;

    @media (min-width: 640px) {
      flex: 1 0 45%;
      margin-left: 5%;
      flex-basis: min-content;
    }

    @media (min-width: 768px) {
      flex: 1 0 auto;
      margin-left: 5%;
      flex-basis: min-content;
    }

    @media (min-width: 1100px) {
      // padding-right: $margin-default;
      margin-left: 56px;
      flex-basis: calc(50% - $margin-default);
    }

    &__text {
      font-weight: normal;
      font-size: 36px;
      line-height: 1.1;
      letter-spacing: -0.05em;
      text-align: center;
      margin: 40px auto 0;

      .text-gradient {
        display: inline-block;
        font-weight: 500;
      }

      @media (min-width: 640px) {
        font-size: 30px;
        margin: 0 auto;
        text-align: left;
      }

      @media (min-width: 980px) {
        font-size: 45px;
        text-align: unset;
        margin: 0;
        max-width: 440px;
      }
    }
  }
}

.about-us {
  border-top: $border-in-dark;
  justify-content: space-evenly;
  align-items: flex-start;
  background-size: cover;
  background-color: $font-color;

  &__text {
    font-size: 29px;
    line-height: 1.1;
    font-weight: 500;
    text-align: left;
    color: $background-color;
    padding: 50px 0;
    margin-left: 20px;

    @media (min-width: 420px) {
      font-size: 36px;
      padding: 60px 0;
    }

    @media (min-width: 980px) {
      margin-left: 60px;
    }
  }

  &__digits {
    width: calc(100% - 40px);
    background: $linear-gradient;
    justify-content: space-around;
    padding: 20px;

    @media (min-width: 768px) {
      padding: 20px 0;
      width: 100%;
    }

    @media (min-width: 980px) {
      padding: $margin-default 0;
    }

    &-content {
      display: inline-flex;
      flex-direction: column;
      padding: 50px 0;
      width: auto;
      text-align: center;
      align-items: center;

      @media (min-width: 768px) {
        align-items: flex-start;
        text-align: left;
      }

      &-subtitle {
        line-height: 1.1;
        max-width: 270px;
        font-size: 23px;
        text-align: center;

        @media (min-width: 768px) {
          text-align: left;
        }

        &.margin {
          @media (min-width: 768px) {
            margin-left: 70px;
            padding-left: 20px;
          }
        }
      }

      &-title {
        line-height: 1.1;
        font-size: 100px;
        margin-bottom: 10px;

        @media (min-width: 687px) {
          font-size: 120px;
        }

        @media (min-width: 768px) {
          font-size: 150px;
        }

        @media (min-width: 980px) {
          font-size: 200px;
        }
      }
    }
  }
}

.works {
  width: 100%;

  &-title {
    padding: 20px;
    font-size: 28px;

    @media (min-width: 980px) {
      padding: calc($margin-default + 1rem) $margin-default;
      font-size: 80px;
    }
  }

  &-examples {
    // @include swiper-wrapper();
    min-height: 80vh;
    width: 100%;
    display: flex;
    overflow-x: auto;
    padding-bottom: 50px;
    margin-bottom: 50px;

    &::-webkit-scrollbar {
      height: 2px;
      width: 100%;
      border: 1px solid $unimportant;
    }

    &::-webkit-scrollbar-thumb {
      height: 4px;
      padding: 2px;
      background-color: $font-color;
    }
  }

  &-slide {
    height: auto;
    position: relative;
    padding: $margin-default;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;
    flex: 1 0 calc(30% - $margin-default * 2);
    border: $border-in-dark;
    border-left: none;
    background-image: url('@/assets/img/cases/brandPromotion/background-work.svg');
    user-select: none;

    &:after {
      content: '';
      position: absolute;
      background-color: $background-color;
      opacity: 1;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      transition: 0.3s ease;
      z-index: 1;
      transition: opacity 0.5s linear;
    }

    &:hover:after {
      opacity: 0;
    }

    &__title, &__button {
      position: relative;
      z-index: 2;
    }
  }
}
</style>
