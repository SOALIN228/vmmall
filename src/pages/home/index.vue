<template>
  <div class="home">
    <header class="g-header-container">
      <home-header></home-header>
    </header>
    <my-scroll :data="recommends"
               pullDown
               @pull-down="pullToRefresh">
      <home-slider></home-slider>
      <home-nav></home-nav>
      <home-recommend @loading="getRecommends"></home-recommend>
    </my-scroll>
    <div class="g-backtop-container"></div>
    <router-view></router-view>
  </div>
</template>

<script>
import MyScroll from 'base/scroll'
import HomeHeader from './header'
import HomeSlider from './slider'
import HomeNav from './nav'
import HomeRecommend from './recommend'

export default {
  name: 'Home',
  components: {
    MyScroll,
    HomeHeader,
    HomeSlider,
    HomeNav,
    HomeRecommend
  },
  data () {
    return {
      recommends: []
    }
  },
  methods: {
    updateScorll () {

    },
    getRecommends (recommends) {
      this.recommends = recommends
    },
    pullToRefresh (end) {
      setTimeout(() => {
        console.log('???')
        end()
      }, 1000)
    }
  }
}
</script>

<style lang="scss" scoped>
  @import "~assets/scss/mixins";

  .home {
    overflow: hidden;
    width: 100%;
    height: 100%;
    background-color: $bgc-theme;
  }

</style>
