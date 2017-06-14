<template>
  <div id="overview">
    <subtitle :titleName="titleName" id="subtitle-overview"></subtitle>
    <div class="container">
      <p v-for="para in introduction">{{para}}</p>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  export default {
    props: ['titleName', 'introduction'],
    components: {
      subtitle: subtitle
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #overview
    .container > p
      font-size 20px
      font-weight 200
      text-indent 2em
      line-height 1.2em
      margin 0

</style>
