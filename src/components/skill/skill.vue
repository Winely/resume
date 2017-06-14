<template>
  <div id="skill">
    <subtitle :titleName="titleName" id="subtitle-skill"></subtitle>
    <div class="content">
      <ul class="skills">
        <li v-for="skill in skills">
          <p>{{skill.name.toUpperCase()}}</p>
          <div class="score-container">
            <svg :style="getLengthStyle(skill)" class="score" xmlns:xlink="http://www.w3.org/1999/xhtml">
              <use xlink:href="#score"></use>
            </svg>
          </div>
        </li>
      </ul>
      <ul class="keys">
        <li v-for="key in keys">{{key}}</li>
      </ul>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  export default {
    components: {
      subtitle
    },
    data () {
      return {
      }
    },
    methods: {
      getLengthStyle: function (skill) {
        return 'width: ' + skill.score * 200 + 'px'
      }
    },
    props: ['skills', 'keys', 'titleName']
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #skill
    .content
      width 80%
      margin 0 10%
      .skills
        tranL=80px
        column-count 2
        column-gap 100px
        list-style none
        margin auto tranL 0 tranL*-1
        li
          padding-bottom 20px
          text-align right
          display flex
          align-items center
          *
            transition-duration 0.2s

        .score-container
          height 10px
          width 200px
          display inline-flex
          background #444
          border-radius 3px
          flex-shrink 0
        .score
          height 10px
          background #EEC057
          border-radius 3px
        p
          margin 0
          display inline-block
          width 50%
          padding-right 20px
      .keys
        margin-top 0
        margin-bottom 28px
        list-style none
        display flex
        justify-content space-between
        flex-wrap wrap
        li
          transition-duration 0.3s
          margin-right 1em
          margin-top 0.8em
          padding 0.3em 1em
          border-radius 999em
          border solid 1px #EEC057
          color #EEC057
</style>
