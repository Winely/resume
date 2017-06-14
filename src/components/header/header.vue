<template>
  <div id='header'>
    <!--<svg class="background" xmlns:xlink="http://www.w3.org/1999/xlink">-->
      <!--<use xlink:href="#headerbg"></use>-->
    <!--</svg>-->
    <div class="container header-content">
      <!--<svg class="icon" xmlns:xlink="http://www.w3.org/1999/xhtml">-->
        <!--<use xlink:href="#headericon"></use>-->
      <!--</svg>-->
      <h1>{{name}}</h1>
      <h3>{{slogan}}</h3>
      <!--<p>{{email}}</p>-->
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    name: 'header',
    props: ['name', 'slogan', 'email']
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  theme= #eec057
#header
  background #333
  margin 0
  overflow hidden
  height 200px
.header-content
  color theme
  h1
    font-size 52px
    padding 0
    margin-bottom 10px
  h3
    font-size 28px
    font-weight 200
    margin-top 10px

</style>
