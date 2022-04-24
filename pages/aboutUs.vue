<template>
  <main class="our-team flex-column">
    <div class="our-team__title">
      <h2>Наша команда</h2>
    </div>
    <section class="our-team__table our-team-flex-rows">
      <div class="our-team__table__peoples flex-column">
        <div class="our-team__table__peoples__item">
          <div v-for="{ name, imgUrl, position } of employees" :key="name + position" class="people flex-column">
            <img class="people-img" :src="require(`@/assets/img/about-us/${imgUrl}.jpg`)" :alt="name">
            <div class="people-info">
              <h4>{{ name.split(' ')[0] }}<br>{{ name.split(' ')[1] }}</h4>
              {{ position }}
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'AboutUsPage',
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
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
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

    h2 {
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
        width: 100%;
        display: inline-grid;
        grid-gap: 3em;

        @media (min-width: 500px) {
          margin-left: auto;
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

  h4 {
    font-weight: normal;
    font-size: 23px;
    line-height: 1.2;
    margin: 0 0 4px 0;
  }

  p {
    font-weight: 600;
    margin: 4px;
    font-size: 14px;
    line-height: 120%;
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
