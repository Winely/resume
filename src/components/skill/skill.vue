<template>
  <div id="skill">
    <subtitle title="专业技能"></subtitle>
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
        skills: [
          {name: 'PHOTOSHOP', score: 0.9},
          {name: 'ILLUSTRATOR', score: 0.8},
          {name: '3d max', score: 0.25},
          {name: 'experience Design', score: 0.5},
          {name: 'PHOTOSHOP', score: 0.9},
          {name: 'PHOTOSHOP', score: 0.9}
        ],
        keys: [
          'Java', 'SEO', 'C++', 'Linux', 'Ruby', 'JavaScipt', 'Java', 'SEO', 'C++', 'Linux'
        ]
      }
    },
    methods: {
      getLengthStyle: function (skill) {
        return 'width: ' + skill.score * 200 + 'px'
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #skill
    /*height 400px*/
    background #4d4d4d
    .content
      width 80%
      padding 90px 0
      margin 0 10%
      .skills
        column-count 2
        column-gap 100px
        list-style none
        li
          padding-bottom 20px
          *
            transition-duration 0.2s
        li:hover
          p
            color #ec8087
          .score
            fill url(#pinkGradient)

        .score-container
          height 10px
          width 200px
          display inline-flex
          background #444
          border-radius 3px
        .score
          height 10px
          fill url(#blue)
          border-radius 3px
        p
          margin 0
          display inline-block
          width 40%
          color #ffffff
      .keys
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
          background #74d8a8
        li:hover
          background #eff27c
</style>
