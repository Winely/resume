<template>
  <div class="subtitle" :id="id">
    <div class="subtitle-content">
      <h2>{{titleName}}</h2>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: ['titleName', 'id']
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .subtitle
    margin 10px 10%
    z-index 999
    transition-duration 0.5s
    box-shadow 0 0 0 0 #aaa
    border-left solid 6px #eec057

  .subtitle-content
    padding 10px 30px
    p,h2
      margin 0 5px
      font-size 22px
      font-weight 500

</style>
