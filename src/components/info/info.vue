<template>
  <div id="info">
    <subtitle title="了解更多"></subtitle>
    <svg class="footer" xmlns:xlink="http://www.w3.org/1999/xlink">
      <use xlink:href="#footer"></use>
    </svg>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  export default {
    components: {
      subtitle
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .footer
    width 100%
    height 450px
    margin-bottom -100px
    background #fff
</style>
