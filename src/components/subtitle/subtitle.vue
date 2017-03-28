<template>
  <div class="subtitle">
    <!--<svg class="subbg" xmlns:xlink="http://www.w3.org/1999/xhtml">-->
      <!--<use xlink:href="#subtitlebg"></use>-->
    <!--</svg>-->
    <div class="subtitle-content">
      <p>—</p>
      <p>{{title}}</p>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: ['title']
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .subtitle
    margin -60px 10%
    background url("red.svg") no-repeat
    background-size 100% 100%
    width 120px
    height 120px
    border-radius 16px
    z-index 999
    position absolute
    transition-duration 0.5s
    box-shadow 0 0 0 0 #aaa
  .subtitle-content
      color #fff
      padding-left 10px
      padding-top 56px
      padding-bottom 20px
      width 100px
      p
        margin 0 5px
        font-size 17px
  .subtitle:hover
    box-shadow 0 0 20px 0 #f5549e
</style>
