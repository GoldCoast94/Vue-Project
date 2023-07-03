<template>
    <div class="header">
      <div>城市选择</div>
      <router-link to="/">
        <div class="iconfont header-back">&#xe65b;</div>
      </router-link>
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
  .header
    overflow: hidden
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: .32rem
    position: relative
    .header-back
      width: .64rem
      font-size: .4rem
      text-align: center
      position: absolute
      top: 0
      left: 0
      color: #fff
</style>
