<template>
  <div id='header'>
    <svg class="background" xmlns:xlink="http://www.w3.org/1999/xlink">
      <use xlink:href="#headerbg"></use>
    </svg>
    <div class="header-content">
      <svg class="icon" xmlns:xlink="http://www.w3.org/1999/xhtml">
        <use xlink:href="#headericon"></use>
      </svg>
      <h1>{{name}}</h1>
      <h3>{{slogan}}</h3>
      <p>{{email}}</p>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    name: 'header',
    data () {
      return {
        name: '何冬怡',
        slogan: '设计是镣铐的舞蹈',
        email: 'me@donggu.me'
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #header
    height 440px
    .background
      position absolute
      z-index -1
      width 100%
      height 800px
    .header-content
      display flex
      flex-direction column
      align-items center
      padding-top 100px
      .icon
        height 35px
        margin-bottom 10px
      h1
        font-size 72px
        margin 0
      h3
        font-size 28px
        font-weight 200
        margin 0
      p
        color #1eb8d9
        font-weight 100
        font-family "Noto Sans S Chinese Thin"
        font-size 22px
        margin 0
</style>
