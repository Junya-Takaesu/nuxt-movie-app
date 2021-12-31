<template>
  <div class="hero">
    <carousel
      :autoplay="true"
      :loop="true"
      :pagination-enabled="false"
      :per-page-custom="[[0, 1]]"
      :autoplay-timeout="5000"
    >
      <slide v-for="i in 7" :key="i">
        <img :src="require(`../assets/imgs/movieHero${i}.jpg`)" />
      </slide>
    </carousel>
    <div class="text-container">
      <div class="text">
        <span class="mini-heading">Now Streaming</span>
        <h1><span>Now</span> Streaming</h1>
        <a href="#movie-grid" class="button">View Movies</a>
      </div>
    </div>
  </div>
</template>

<script>
import Carousel from 'vue-carousel/src/Carousel.vue'
import Slide from 'vue-carousel/src/Slide.vue'

export default {
  name: 'Hero',
  components: {
    Carousel,
    Slide,
  },
}
</script>

<style lang="scss" scoped>
.hero {
  height: 400px;
  position: relative;

  &::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.6);
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .text-container {
    z-index: 99;
    position: absolute;
    top: 0;
    margin: 0;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;

    .text {
      padding: 0 16px;
      width: 100%;
      max-width: 1400px;
      margin: 0 auto;
    }

    .mini-heading {
      font-weight: 600;
      font-size: 18px;
      text-transform: uppercase;
      color: #c92502;
      margin-bottom: 8px;
    }

    h1 {
      color: #fff;
      font-size: 64px;
      font-weight: 200;
      margin-bottom: 8px;

      span {
        font-weight: 500;
      }
    }

    .button {
      font-size: 20px;
      align-self: flex-start;
    }
  }

  @media (min-width: 750px) {
    height: 500px;

    .text-container {
      h1 {
        font-size: 84px;
      }

      .mini-heading {
        font-size: 22px;
      }
    }
  }
}
</style>

<style lang="scss">
/* scoped のスタイルだと、適用されないので、unscoped でスタイルを定義 */
.VueCarousel {
  height: 100%;
  * {
    height: 100% !important;
  }
}
</style>
