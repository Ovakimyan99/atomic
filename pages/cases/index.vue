<template>
  <section class="cases">
    <div class="cases-path text-gradient">
      <AppPageTitle class="cases-title text-gradient">
        Кейсы
      </AppPageTitle>
    </div>
    <div class="cases-path cases-path--content">
      <ul class="cases-path__pages-list">
        <li v-for="{ name, imgUrl } of cases" :key="name" class="cases-path__pages">
          <router-link class="cases-path__pages-link" to="/cases/brandPromotion">
            <img class="cases-path__pages-img" :src="require(`~/assets/img/cases/${imgUrl}`)" :alt="name">
            <h3 class="cases-path__pages-title">
              {{ name }}
            </h3>
          </router-link>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import AppPageTitle from '@/components/basePage/PageTitle.vue'

export default {
  name: 'CasesMainPage',
  components: {
    AppPageTitle
  },
  data() {
    return {
      cases: [
        {
          name: "Arc'teryx",
          imgUrl: 'architecture/architecture.jpg'
        },
        {
          name: 'Antiperspirant',
          imgUrl: 'antiperspirant/antiperspirant.jpg'
        },
        {
          name: 'Brand Promotion',
          imgUrl: 'brandPromotion/brandPromotion.jpg'
        },
        {
          name: 'Cosiness',
          imgUrl: 'cosiness/cosiness.jpg'
        },
        {
          name: 'modeling',
          imgUrl: 'modeling/modeling.jpg'
        },
        {
          name: 'Positioning',
          imgUrl: 'positioning/positioning.jpg'
        },
        {
          name: 'Restaurant',
          imgUrl: 'restaurant/restaurant.jpg'
        },
        {
          name: 'Street',
          imgUrl: 'street/street.jpg'
        },
        {
          name: 'Sunset',
          imgUrl: 'sunset/sunset.jpg'
        },
        {
          name: 'Visual Design',
          imgUrl: 'visualDesign/visualDesign.jpg'
        },
        {
          name: 'Weightlessness',
          imgUrl: 'weightlessness/weightlessness.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.cases {
  background-color: $background-color;
  display: block;

  @media (min-width: 540px) {
    display: flex;
  }

  &-title {
    position: sticky;
    top: 20vh;
    @include textGradient();
  }

  &-path {
    padding-top: 150px;
    padding-left: 30px;
    flex: 1;

    @media (min-width: 540px) {
      padding-bottom: 60px;
    }

    @media (min-width: 980px) {
      padding-left: 60px;
    }

    @media (min-width: 1080px) {
      padding: 174px 0 40px 60px;
    }

    @media (min-width: 1115px) {
      padding-top: 140px;
      padding-bottom: 60px;
    }

    &--content {
      flex: 2;
      padding-top: 50px;
      padding-bottom: 60px;
      padding-left: 0;

      @media (min-width: 540px) {
        border-top: 0;
        padding-top: 150px;
        padding-right: 30px;
        flex: 1;
      }

      @media (min-width: 980px) {
        flex: 3;
        padding-right: 70px;
      }

      @media (min-width: 1080px) {
        padding-top: 174px;
      }

      @media (min-width: 1115px) {
        padding-left: 50px;
        padding-top: 285px;
      }
    }

    &__pages {
      margin: 0 0 0 auto;
      width: 100%;

      @media (min-width: 420px) {
        max-width: 280px;
      }

      &-list {
        list-style-type: none;
        display: grid;
        grid-template-columns: repeat(1, 1fr);
        justify-content: space-between;
        margin: 20px;
        width: 85%;
        margin: auto;
        grid-gap: 2em;

        @media (min-width: 540px) {
          grid-template-columns: repeat(1, 1fr);
          grid-gap: 2em;
          margin: 0 0 0 auto;
          width: 100%;
        }

        @media (min-width: 940px) {
          max-width: 640px;
          grid-template-columns: repeat(2, 1fr);
          grid-gap: 4em 3em;
        }
        @media (min-width: 1080px) {
          margin-left: auto;
        }
        @media (min-width: 1320px) {
          grid-template-columns: repeat(3, 1fr);
          max-width: none;
          width: auto;
          margin: auto;
          margin-right: 40px;
        }
      }

      &-link {
        display: inline-flex;
        flex-direction: column;
        text-decoration: none;
        width: 100%;
      }

      &-img {
        width: 100%;
        object-fit: cover;

        height: 280px;

        @media (min-width: 420px) {
          width: 280px;
        }
      }

      &-title {
        display: inline-block;
        font-size: 24px;
        line-height: 1.2;
        color: $font-color;
        margin-top: 30px;
      }
    }
  }
}
</style>
