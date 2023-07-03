<template>
    <div>
      <router-link class="header-abs" tag="div" to="/" v-show="showABS">
        <span class="iconfont header-abs-back">&#xe65b;</span>
      </router-link>
      <div
       class="header-fixed"
       v-show="!showABS"
       :style="opacityStyle"
      >
        <router-link to="/">
          <div class="iconfont header-fixed-back">&#xe65b;</div>
        </router-link>
        <span>景点介绍</span>
      </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showABS: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showABS = false
      } else {
        this.showABS = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
  .header-abs
    position: absolute
    top: .2rem
    left: .2rem
    width: .8rem
    height: .8rem
    line-height: .8rem
    text-align: center
    border-radius: .4rem
    background: rgba(0,0,0,0.6)
    .header-abs-back
      color: #ffffff
  .header-fixed
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: .32rem
    position: fixed
    top: 0
    left: 0
    right: 0
    .header-fixed-back
      width: .64rem
      font-size: .4rem
      text-align: center
      position: absolute
      top: 0
      left: 0
      color: #fff
</style>
