<template>
  <section class="work-dynamics">
    <section class="work-dynamics__empty">
      <h2 class="work-dynamics__empty-title">
        <span class="work-dynamics__empty-gradient text-gradient">Arc'teryx</span>
        <span class="work-dynamics__empty-accent">Гонка за контентом</span>
      </h2>
    </section>
    <!-- проект -->
    <section class="work-dynamics__project">
      <img class="work-dynamics__project-img" src="@/assets/img/cases/brandPromotion/Arcteryx_3_compressed.png">
    </section>
    <!-- о кейсе -->
    <section class="work-dynamics__case">
      <h3 class="work-dynamics__case-title">
        О кейсе
      </h3>
      <div class="work-dynamics__case-main">
        <div class="work-dynamics__case-text-wrapper">
          <p class="work-dynamics__case-text">
            Перед нами стояла важная задача – раскрыть технологические преимущества продукции бренда <b>Arc'teryx</b> за счет релевантных для аудитории инфлюенсеров и их соцсетей.
          </p>
          <p class="work-dynamics__case-text">
            Мы придумали и реализовали проект, в котором два популярных блогера: <b>Руслан Усачев и Макс +100500</b> поедут далеко за полярный круг в Териберку и протестируют все преимущества одежды <b>Arc'teryx</b>.
          </p>
          <p class="work-dynamics__case-text">
            “ГОНКА ЗА КОНТЕНТОМ” — так называется проект, где два топовых блогера соревнуются между собой, чтобы получить лучшие фото и видео. А получить по-настоящему крутой контент им помогла одежда <b>Arc'teryx</b>.
          </p>
        </div>
        <ul class="work-dynamics__case-list">
          <li class="work-dynamics__case-phase">
            Разработка креативной концепции проекта
          </li>
          <li class="work-dynamics__case-phase">
            Подбор релевантных инфлюенсеров для кампании
          </li>
          <li class="work-dynamics__case-phase">
            Скаутинг и менеджмент контента инфлюенсеров
          </li>
          <li class="work-dynamics__case-phase">
            Организация поездки в Териберку
          </li>
          <li class="work-dynamics__case-phase">
            Продакшн видеоролика
          </li>
          <li class="work-dynamics__case-phase">
            Контроль исполнения проекта
          </li>
          <li class="work-dynamics__case-phase">
            Более 1 млн. просмотров на сторис
          </li>
          <li class="work-dynamics__case-phase">
            Более 500 тыс. охват постов
          </li>
        </ul>
        <div class="work-dynamics__case-cta">
          <AppButton class="work-dynamics__case-cta-btn">
            Перейти на сайт проекта
          </AppButton>
        </div>
      </div>
    </section>
    <!-- product -->
    <section class="work-dynamics__product">
      <h3 class="work-dynamics__product-title">
        Продакшн
      </h3>
      <div class="work-dynamics__product-path work-dynamics__product-video">
        <img class="work-dynamics__product-path__img" src="@/assets/img/cases/brandPromotion/Rectangle_63.png">
      </div>
      <div class="work-dynamics__product-path">
        <img class="work-dynamics__product-path__img" src="@/assets/img/cases/brandPromotion/Arcteryx_3_compressed-3.png">
      </div>
      <div class="work-dynamics__product-path">
        <img class="work-dynamics__product-path__img" src="@/assets/img/cases/brandPromotion/Arcteryx_3_compressed-6.png">
      </div>
      <div class="work-dynamics__product-path">
        <img class="work-dynamics__product-path__img" src="@/assets/img/cases/brandPromotion/Arcteryx_3_compressed-2.png">
      </div>
      <div class="work-dynamics__product-path work-dynamics__product-path__double drup_img">
        <img class="work-dynamics__product-path__img drup_img_bg" src="@/assets/img/cases/brandPromotion/Rectangle_69.png">
        <img class="work-dynamics__product-path__img drup_img_bg" src="@/assets/img/cases/brandPromotion/Rectangle_70.png">
      </div>
    </section>
    <!-- cta -->
    <div class="work-dynamics__cta">
      <AppButton class="work-dynamics__cta-btn">
        Инстаграм Макса +100500
      </AppButton>
      <AppButton class="work-dynamics__cta-btn">
        Инстаграм Руслана Усачева
      </AppButton>
      <AppButton class="work-dynamics__cta-btn">
        Посмотреть все видео для этого проекта
      </AppButton>
    </div>
  </section>
</template>

<script>
import AppButton from '@/components/base/MainButton.vue'
export default {
  name: 'BrandPromotion',
  components: {
    AppButton
  },
  layout: 'CasesPage'
}
</script>

<style lang="scss" scoped>
.work-dynamics {
  background-color: $font-color;

  &__empty {
    min-height: 40vh;
    display: flex;
    background-color: $font-color;
    color: $background-color;

    &_last {
      min-height: 35vh;
      @media (min-width: 980px) {
        min-height: 80vh;
      }
    }

    @media (min-width: 1080px) {
      min-height: 60vh;
    }

    &-title {
      padding: 25px;
      height: min-content;
      margin-top: auto;
      font-size: 34px;
      line-height: 1.1;
      @media (min-width: 680px) {
        font-size: 46px;
      }
      @media (min-width: 980px) {
        font-size: 60px;
      }
      @media (min-width: 1080px) {
        font-size: 90px;
        padding: 65px;
      }
    }

    &-gradient {
      font-family: $font-family;
      font-size: 30px;
      line-height: 1;
      margin-bottom: 10px;
      display: inline-block;
      width: max-content;

      @media (min-width: 980px) {
        margin-bottom: 20px;
      }
      @media (min-width: 1080px) {
        margin-bottom: 31px;
      }
    }

    &-accent {
      display: block;
    }
  }

  &__project {
    height: auto;
    overflow: hidden;

    &-img {
      width: 100%;
      object-fit: cover;
    }
  }

  &__case {
    display: block;
    color: $background-color;
    @media (min-width: 980px) {
      display: flex;
    }

    &-title {
      margin: 0;
      width: auto;
      border-right: none;
      border-bottom: $border-in-light;
      padding: 18px 26px;
      font-weight: 600;
      font-size: 30px;
      flex: 1;
      @media (min-width: 980px) {
        padding: 63px;
        border-right: $border-in-light;
        width: 40%;
      }
    }

    &-main {
      flex: 4;
    }

    &-text {
      font-weight: 400;
      font-size: 18px;
      line-height: 1.3;
      @media (min-width: 980px) {
        font-size: 23px;
      }
      b {
        font-weight: 700;
      }

      &:not(:last-child) {
        margin-bottom: 30px;
      }

      &-wrapper {
        padding: 18px 26px;
        border-bottom: $border-in-light;
        @media (min-width: 980px) {
          padding: 70px 65px 70px 70px;
        }
      }
    }

    &-list {
      padding: 18px 26px;
      list-style: none;
      display: flex;
      flex-direction: column;
      margin: 0;
      @media (min-width: 980px) {
        padding: 70px 65px 77px 70px;
      }
    }

    &-phase {
      border-bottom: 1px solid $background-color;
      font-size: 16px;
      line-height: 1.3;
      padding-bottom: 22px;
      @media (min-width: 980px) {
        font-size: 23px;
      }
      &:not(:last-child) {
        margin-bottom: 28px;
      }
    }

    &-cta {
      padding: 40px 26px;
      background-color: $background-color;

      @media (min-width: 980px) {
        padding: 60px 65px;
      }

      &-btn {
        width: 100%;
        margin: auto;
        max-width: 500px;
        background-color: transparent;
        @media (min-width: 980px) {
          max-width: none;
        }
      }
    }
  }

  &__product {
    padding: 18px 26px;

    @media (min-width: 980px) {
      padding: 70px 65px 100px;
    }

    &-title {
      font-size: 30px;
      line-height: 25px;
      margin-bottom: 40px;
      color: #000;
      @media (min-width: 980px) {
        margin-bottom: 70px;
      }
    }

    &-path {
      justify-content: space-between;
      display: flex;

      @media (min-width: 1400px) {
        display: flex;
      }

      &:not(:last-child) {
        margin-bottom: 20px;

        @media (min-width: 980px) {
          margin-bottom: 70px;
        }
      }

      &__img {
        width: 100%;
        height: 100%;
      }

      &__double &__img {
        flex: 1;

        &:not(:last-child) {
          margin-right: 70px;
        }
      }
    }
  }

  &__cta {
    padding: 40px 26px;
    background-color: $background-color;
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;

    @media (min-width: 980px) {
      flex-direction: row;
      padding: 60px 65px;
    }

    &-btn {
      flex: 1;
      width: auto;
      margin-right: 0;

      @media (min-width: 980px) {
        width: fit-content;
      }

      &:first-child {
        margin-right: 0;
        margin-bottom: 20px;

        @media (min-width: 980px) {
          margin-right: 70px;
          margin-bottom: 0;
        }
      }

      &:last-child {
        margin-right: 0;
        flex: 2;
        margin-top: 20px;
        flex-basis: 100%;

        @media (min-width: 980px) {
          margin-top: 35px;
        }
      }
    }
  }
}
.running-button__content-text {
  margin-right: auto;
  font-size: 12px !important;
  @media (min-width: 980px) {
    font-size: 15px;
  }
}
.drup_img {
  flex-direction: column;

  @media (min-width: 980px) {
    flex-direction: row;
  }

  &_bg {
    width: 100%;

    &:first-child {
      margin-right: 0 !important;
      margin-bottom: 20px;
      @media (min-width: 980px) {
        margin-right: 70px !important;
        margin-bottom: 0;
      }
    }

    @media (min-width: 980px) {
    width: calc(50% - 50px);
    }
  }
}
</style>
