<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" class="banner-img">
      <div class="banner-info">
        <div class="banner-title">
          北京天安门(AAAA景区)
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe689;</span>
          39
        </div>
      </div>
    </div>
    <common-fade>
      <common-gallary :imgs="imgs" v-show="showGallary" @close="handleBannerClose"></common-gallary>
    </common-fade>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import CommonFade from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary,
    CommonFade
  },
  data () {
    return {
      imgs: [
        'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg',
        'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg'
      ],
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleBannerClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-title
        flex: 1
        display: flex
        align-items: center
        font-size: .32rem
        padding-left: .2rem
      .banner-number
        padding: .2rem
        height: .32rem
        line-height: .32rem
        border-radius: .2rem
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
