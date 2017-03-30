<template>
  <div class="info">
    <subtitle :titleName="titleName" id="subtitle-info"></subtitle>
    <div class="content">
      <div v-if="blog" class="blog">
        <a :href="blog.protocol+'://'+blog.url" target="_blank">
          <i class="iconfont icon-iconblog2"></i>
          {{blog.url}}
        </a>
      </div>
      <div v-if="github" class="github">
        <a :href="github.protocol+'://'+github.url" target="_blank">
          <i class="iconfont icon-github"></i>
          {{github.url}}
        </a>
      </div>
      <div v-if="email" class="email">
        <a :href="'mailto:'+email" target="_blank">
          <i class="iconfont icon-email"></i>
          {{email}}
        </a>
      </div>
    </div>
    <svg class="footer" xmlns:xlink="http://www.w3.org/1999/xlink">
      <use xlink:href="#footer"></use>
    </svg>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  export default {
    props: ['github', 'blog', 'email', 'titleName'],
    components: {
      subtitle
    }
//    data () {
//      return {
//        github: 'github.com/Winely',
//        blog: 'donggu.me',
//        email: 'me@donggu.me'
//      }
//    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .footer
    width 100%
    height 450px
    margin-bottom -100px
    background #fff
    bottom 0
    position absolute
    z-index -1

  .info
    position relative
    height 300px
    .content
      display flex
      justify-content space-around
      width 60%
      margin auto
      padding-top 150px
      z-index 999
      div
        text-align center
        font-size 16px
        a
          text-decoration none
          color #2BA0B4
        .iconfont
          font-size 56px
          display block
          transition-duration .3s
      div:hover
        .iconfont
          font-size 92px
</style>
