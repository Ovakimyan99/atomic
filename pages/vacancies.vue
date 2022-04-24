<template>
  <section class="vacancies">
    <div class="vacancies-header">
      <AppPageTitle class="text-gradient">
        Вакансии
      </AppPageTitle>
    </div>
    <section class="vacancies-content">
      <span class="vacancies-content__circle" />
      <p class="vacancies-content__text">
        Будем рады<br>
        работать вместе.<br>
        Стань частью нашей<br>
        команды.
      </p>
    </section>
    <section class="vacancies-main">
      <div id="vacancies-list" class="vacancies-main__marketing">
        <span class="vacancies-main__marketing-title">Открытые вакансии</span>
        <ul class="vacancies-main__marketing-list">
          <li v-for="n of 3" :key="n" class="vacancies-main__marketing-item">
            <span class="vacancies-main__marketing-item--info">Маркетолог,</span>
            <span class="vacancies-main__marketing-item--info">полная занятость</span>
            <span class="vacancies-main__marketing-item--info">[Москва]</span>
            <button class="vacancies-main__marketing-item-btn">
              Откликнуться
            </button>
          </li>
        </ul>
      </div>
    </section>
  </section>
</template>

<script>
import AppPageTitle from '@/components/basePage/PageTitle.vue'

export default {
  name: 'VacanciesPage',
  components: {
    AppPageTitle
  }
}
</script>

<style lang="scss" scoped>
@mixin blackBtn {
  font-weight: 500;
  font-size: 14px;
  background-color: $background-color;
  text-decoration: none;
  color: $font-color;
  display: inline-block;
  border-radius: 50px;
}

.vacancies {
  color: $font-color;
  background-color: $background-color;
  overflow: hidden;

  &-header {
    display: block;
    margin: 100px 30px 50px;

    @media (min-width: 980px) {
      margin: 150px $margin-default 75px;
    }
  }

  &-content {
    display: flex;
    align-items: center;
    margin-bottom: 70px;

    &__circle {
      width: 280px;
      height: 280px;
      border-radius: 50%;
      transform: translateX(-20%);
      background: $linear-gradient;

      @media (min-width: 420px) {
        width: 400px;
        height: 400px;
      }

      @media (min-width: 687px) {
        width: 500px;
        height: 500px;
      }

      @media (min-width: 980px) {
        width: 600px;
        height: 600px;
      }

      @media (min-width: 1300px) {
        width: 45vw;
        height: 45vw;
      }
    }

    &__text {
      font-size: 24px;
      line-height: 1.2;
      position: absolute;
      transform: translateX(-50%);
      left: 50%;
      width: max-content;

      @media (min-width: 687px) {
        font-size: 36px;
      }

      @media (min-width: 1100px) {
        font-size: 40px;
        margin-left: 100px;
        position: relative;
        left: 0;
        transform: none;
      }
    }
  }

  &-main {
    width: 100%;
    color: $font-color;
    padding-bottom: 100px;

    &-title {
      font-weight: 400;
      margin: 64px 0 20px 32px;
      font-size: 36px;

      @media (min-width: 1000px) {
        margin-left: 60px;
      }
    }

    &__marketing {
      margin: 0 32px;

      &-title {
        font-size: 27px;
        line-height: 1;
        display: block;
        margin-bottom: 35px;

        @media (min-width: 560px) {
          font-size: 30px;
          margin-bottom: 40px;
        }

        @media (min-width: 1000px) {
          font-size: 36px;
          margin-bottom: 55px;
        }
      }

      &-list {
        display: flex;
        flex-direction: column;
        padding: 0;
        margin: 0;
      }

      &-item {
        display: flex;
        overflow: hidden;
        flex-wrap: wrap;
        justify-content: space-between;
        background-color: transparent;
        padding: 16px 0;
        border-radius: 8px;

        @media (min-width: 687px) {
          border-radius: 24px;
          flex-wrap: nowrap;
          border-radius: 50px;
          padding: 0;
          justify-content: flex-start;
          border-radius: 40px;
        }

        @media (min-width: 900px) {
          flex-wrap: nowrap;
        }

        &:not(:last-child) {
          margin-bottom: 20px;
        }

        &-btn {
          position: relative;
          flex: 1;
          font-size: 17px;
          line-height: 1;
          padding: 13px 35px;

          margin-top: 11px;
          flex: 1 0 80%;
          margin: 8px auto 0;
          @include blackBtn();
          background: linear-gradient($background-color, $background-color) padding-box, $linear-gradient border-box;
          border: 1px solid transparent;
          border-radius: 40px;
          letter-spacing: 1px;
          margin-top: 16px;

          @media (min-width: 687px) {
            flex: none;
            padding: 18px 50px;
            margin: 0;
            margin-left: auto;
          }
        }

        &--info {
          line-height: 1;
          display: inline-block;
          flex: 1 0 50%;
          font-size: 16px;

          display: flex;
          align-items: center;
          justify-content: center;
          text-align: center;

          &:first-child {
            flex: 1 0 100%;
            margin-bottom: 9px;
          }

          @media (min-width: 687px) {
            font-size: 20px;
            flex: none;
            background-color: transparent;
            padding: 8px 4px;

            &:first-child {
              flex: none;
              margin-bottom: 0;
              padding-left: 20px;
            }
          }

          @media (min-width: 768px) {
            font-size: 23px;
          }
        }
      }
    }
  }
}
</style>
