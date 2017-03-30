<template>
  <div id="overview">
    <subtitle :titleName="titleName" id="subtitle-overview"></subtitle>
    <div class="container">
      <p v-for="para in introduction">{{para}}</p>
      <edu :eduinfo="eduinfo"></edu>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  import edu from '../edu/edu'
  export default {
    props: ['titleName', 'introduction', 'eduinfo'],
    components: {
      subtitle: subtitle,
      edu: edu
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #overview
    .container
      padding-top 80px
    .container > p
      font-size 20px
      font-weight 200
      text-indent 2em
      line-height 1.2em
      margin 0

    margin-bottom 100px
</style>
