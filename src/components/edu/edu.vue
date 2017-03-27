<template>
  <div id="edu">
    <div class="edu-block edu-left">
      <div class="upper">
        <p class="large-label">GPA</p>
        <p> {{gpa}}/{{gpaSum}}</p>
      </div>
      <div class="down">
        <p>{{gpaRank}}</p>
        <p>—</p>
      </div>
    </div>
    <div class="edu-block edu-school">
      <div class="upper">
        <p>—</p>
        <p>{{degree}}</p>
      </div>
      <div class="down">
        <p>{{time.from}}~{{time.to}} {{major}}</p>
        <p class="large-label">{{college}}</p>
      </div>
    </div>

    <div class="edu-block edu-right">
      <div class="content" v-for="award in awards">
        <p class="sub-award">{{award.sub}}</p>
        <p class="main-award">{{award.main}}</p>
      </div>
      <div class="down">
        <p>校内活动</p>
        <p>—</p>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    data () {
      return {
        gpa: 4.2,
        gpaSum: 5.0,
        gpaRank: '前20%',
        degree: '本科',
        college: '同济大学',
        major: '软件工程',
        time: {
          from: 2014,
          to: 2018
        },
        awards: [
          {
            sub: '同济大学学生会传媒部',
            main: '设计统筹处干事'
          },
          {
            sub: '微软俱乐部颁发的',
            main: '“微软之星”奖状'
          }
        ]
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #edu
    display flex
    width 750px
    margin 30px auto
    box-shadow 0 0 15px 2px #bbb

  .edu-block
    color #fff
    width 250px
    height 250px
    margin 0
    background #ddd
    display flex
    flex-direction column
    justify-content space-between
    div
      margin-left 24px
    .upper
      margin-top 24px
    .down
      margin-bottom 20px
    p
      width 200px
      margin 5px
      font-size 20px
      line-height 1em
    .large-label
      vertical-align text-top
      text-indent -4px
      font-size 36px
      font-weight 600
      margin-bottom 0.3em

  .edu-school
    background url('./background.svg') no-repeat
    background-size cover
    color #000

  .edu-right
    text-align end
    .content
      margin-top 20px
    .main-award
      font-size 24px
      font-weight 600
</style>
