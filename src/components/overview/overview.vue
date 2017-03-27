<template>
  <div id="overview">
    <subtitle title="个人简介"></subtitle>
    <div class="container">
      <p v-for="para in introduction">{{para}}</p>
      <edu></edu>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  import edu from '../edu/edu'
  export default {
    components: {
      subtitle: subtitle,
      edu: edu
    },
    data () {
      return {
        introduction: [
          '是非成败转头空，青山依旧在，惯看秋月春风。一壶浊酒喜相逢，古今多少事，滚滚长江东逝水，浪花淘尽英雄。 几度夕阳红。白发渔樵江渚上，都付笑谈中。',
          '是非成败转头空，青山依旧在，惯看秋月春风。一壶浊酒喜相逢，古今多少事，滚滚长江东逝水，浪花淘尽英雄。 几度夕阳红。白发渔樵江渚上，都付笑谈中。',
          '是非成败转头空，青山依旧在，惯看秋月春风。一壶浊酒喜相逢，古今多少事，滚滚长江东逝水，浪花淘尽英雄。 几度夕阳红。白发渔樵江渚上，都付笑谈中。',
          '是非成败转头空，青山依旧在，惯看秋月春风。一壶浊酒喜相逢，古今多少事，滚滚长江东逝水，浪花淘尽英雄。 几度夕阳红。白发渔樵江渚上，都付笑谈中。'
        ]
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
#overview
  .container
    padding-top 80px
  .container>p
    font-size 20px
    font-weight 200
    text-indent 2em
    line-height 1.2em
    margin 0

  margin-bottom 100px
</style>
