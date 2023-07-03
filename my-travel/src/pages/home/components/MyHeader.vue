<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe65b;</div>
        </div>
        <div class="header-input iconfont">
            <span class="search">&#xe608;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link to="/city">
        <div class="header-right iconfont">
            {{this.city}}
            <span class="arrow-icon">&#xe605;</span>
        </div>
        </router-link>
    </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'MyHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style scoped lang='stylus'>
@import '~styles/variables.styl'
  .header
    line-height: $headerHeight
    display: flex
    background-color: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      padding-left: .2rem
      .back-icon
        font-size: .4rem
        text-align: center
    .header-input
      height: .62rem
      line-height: .62rem
      margin:.12rem 0 0 .2rem
      flex: 1
      color:#ccc
      background: #ffffff
      border-radius: .1rem
      .search
        margin: 0 .1rem 0 .2rem
    .header-right
      min-width: 1.04rem
      padding: .1rem
      float: right
      text-align: center
      color: white
      .arrow-icon
        font-size: .24rem
        margin-left: -.04rem
</style>
