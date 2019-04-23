<template>
  <div class="home">
    <header class="g-header-container">
      <home-header></home-header>
    </header>
    <my-scroll>
      <home-slider></home-slider>
      <home-nav></home-nav>
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

export default {
  name: 'Home',
  components: {
    MyScroll,
    HomeHeader,
    HomeSlider,
    HomeNav
  },
  data () {
    return {}
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
