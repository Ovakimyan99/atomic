<template>
  <main class="our-team flex-column">
    <AppPageTitle class="text-gradient about-title">
      О нас
    </AppPageTitle>
    <AppSquareScreen class="revert" :revers="true">
      <template #IntegralPart>
        <h2 class="priorities-title">
          Наши приоритеты
        </h2>
        <div class="priorities-circle" />
      </template>
      <template #CrushedParts>
        <AppSquareInfo class="priorities-square-info">
          <template #title>
            Любим то,<br>что делаем
          </template>
        </AppSquareInfo>
        <AppSquareInfo class="priorities-square-info">
          <template #title>
            Делимся<br>опытом
          </template>
        </AppSquareInfo>
        <AppSquareInfo class="priorities-square-info">
          <template #title>
            Учимся<br>всегда<br>и везде
          </template>
        </AppSquareInfo>
        <AppSquareInfo class="priorities-square-info">
          <template #title>
            Смотрим в<br>будущее
          </template>
        </AppSquareInfo>
      </template>
    </AppSquareScreen>

    <div class="our-team__title">
      <h2 class="our-team__title-text">
        Наша команда
      </h2>
    </div>
    <section class="our-team__table our-team-flex-rows">
      <div class="our-team__table__peoples flex-column">
        <div class="our-team__table__peoples__item">
          <div v-for="{ name, imgUrl, position } of employees" :key="name + position" class="people flex-column">
            <img class="people-img" :src="require(`@/assets/img/about-us/${imgUrl}.jpg`)" :alt="name">
            <div class="people-info">
              <h4 class="people-info__name">
                {{ name.split(' ')[0] }}<br>{{ name.split(' ')[1] }}
              </h4>
              {{ position }}
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import AppSquareInfo from '@/components/base/SquareInfo.vue'
import AppSquareScreen from '@/components/base/SquareScreen.vue'
import AppPageTitle from '@/components/basePage/PageTitle.vue'

export default {
  name: 'AboutUsPage',
  components: {
    AppSquareInfo,
    AppSquareScreen,
    AppPageTitle
  },
  data() {
    return {
      employees: [
        {
          name: 'Юлия Васянович',
          imgUrl: 'ulia',
          position: 'Финансовый менеджер'
        },
        {
          name: 'Кристина Кочеткова',
          imgUrl: 'kristina',
          position: 'Директор по работе с клиентами'
        },
        {
          name: 'Виталий Харитонов',
          imgUrl: 'noname',
          position: 'Генеральный директор'
        }
      ],
      squareInfo: [
        {
          title: 'Любим то, что делаем'
        },
        {
          title: 'Делимся опытом'
        },
        {
          title: 'Учимся всегда и везде'
        },
        {
          title: 'Смотрим в будущее'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.about-title {
  margin: 20vh 10px 90px 26px;
  line-height: 1.1;
  font-size: 39px;
  display: inline;
  width: max-content;

  @media (min-width: 760px) {
    font-size: 45px;
  }

  @media (min-width: 980px) {
    margin: 20vh $margin-default 70px;
  }

  @media (min-width: 1080px) {
    font-size: 60px;
    margin-bottom: 10vh;
  }
}

.priorities {
  &-title {
    margin-bottom: 20px;
    font-weight: normal;
    font-size: 32px;
    line-height: 1.1;

    @media (min-width: 400px) {
      font-size: 38px;
    }

    @media (min-width: 600px) {
      font-size: 42px;
    }

    @media (min-width: 1000px) {
      font-size: 48px;
    }
  }

  &-circle {
    background-image: url('@/assets/img/about-us/atom-circle.svg');
    background-repeat: round;
    background-size: calc(100% / 10);
    width: 100%;
    height: 50%;
    margin-top: auto;

    @media (min-width: 520px) {
      background-size: calc(100% / 15);
    }
  }

  &-square-info, &-square-info:hover {
    background-color: $background-color;
    color: $font-color;
    cursor: default;
    border: $border-in-dark;
    border-bottom: none;
    border-left: none;
  }
}

.our-team {
  &-flex-rows {
    display: flex;
    flex-direction: column;

    @media (min-width: 800px) {
      flex-direction: row;
    }
  }

  &__title {
    border: $border-in-light;
    padding: 40px 20px;

    @media (min-width: 980px) {
      padding: $margin-default;
    }

    &-text {
      text-align: left;
      font-weight: normal;
      font-size: 32px;
      line-height: 1.1;

      @media (min-width: 500px) {
        text-align: unset;
        font-size: 40px;
      }

      @media (min-width: 640px) {
        font-size: 48px;
      }
    }
  }

  &__table {

    &__peoples {
      @media (min-width: 650px) {
        padding: 0;
      }

      &__item {
        border: none;
        padding: 20px;
        grid-template-columns: repeat(1, 1fr);
        display: inline-grid;
        grid-gap: 3em;

        @media (min-width: 500px) {
          margin-left: auto;
          width: calc(100% - 40px);
        }

        @media (min-width: 560px) {
          grid-template-columns: repeat(2, 1fr);
          justify-items: center;
        }

        @media (min-width: 800px) {
          grid-template-columns: repeat(2, 1fr);
          justify-items: center;
        }

        @media (min-width: 980px) {
          padding: $margin-default;
        }

        @media (min-width: 1000px) {
          padding: 30px 20px $margin-default * 2;
          grid-template-columns: repeat(3, 1fr);
          border: $border-in-light;
          width: 80%;
        }
      }
    }
  }
}

.people {
  color: $font-color;
  margin: auto;

  @media (min-width: 500px) {
    max-width: 400px;
  }

  &-info {
    &__name {
      font-weight: normal;
      font-size: 23px;
      line-height: 1.2;
      margin: 0 0 4px 0;
    }

    &__position {
      font-weight: 600;
      margin: 4px;
      font-size: 14px;
      line-height: 120%;
    }
  }

  &-img {
    width: 100%;
    object-fit: cover;
  }

  &-info {
    margin: 30px 0 0 0;
    padding: 0 0 0 10px;
  }
}
</style>
