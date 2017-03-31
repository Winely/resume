<template>
  <div class="projects">
    <subtitle :titleName="titleName" id="subtitle-project"></subtitle>
    <div class="content" on>
      <div class="go go-left" @click="amount--" v-show="amount!=0">
        <i class="iconfont icon-left"></i>
      </div>
      <div class="go go-right" @click="amount++" v-show="amount!=projects.length-1">
        <i class="iconfont icon-right"></i>
      </div>
      <div class="viewer">
        <ul class="scrollpad" :style="getStyle">
          <li v-for="(project, index) in projects" :id="'project'+ (index+1)">
            <div class="description" @click="newTab(project.link)">
              <div v-for="item in project.description" class="container">
                <h4>{{item.title}}</h4>
                <p>{{item.content}}</p>
              </div>
            </div>
            <thumbnail :imgSrc="'./static/'+project.img" width="60%" height="400px"></thumbnail>
            <svg v-if="index===0" class="banner start-banner">
              <use xlink:href="#banner-start"></use>
            </svg>
            <svg v-else-if="index<projects.length-1" class="banner middle-banner">
              <use xlink:href="#banner-middle"></use>
            </svg>
            <svg v-else class="banner end-banner">
              <use xlink:href="#banner-end"></use>
            </svg>
            <h4 @click="newTab(project.link)">{{project.name}}</h4>
            <p @click="newTab(project.link)">{{project.from}} ~ {{project.to}}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  import thumbnail from '../thumbnail/thumbnail'
  export default {
    components: {
      subtitle,
      thumbnail
    },
    methods: {
      newTab: function (link) {
        if (link.isEmpty) return
        window.open(link)
      }
    },
    computed: {
      getStyle: function () {
        return 'margin-left: -' + this.amount * 100 + '%; width:' + this.projects.length * 100 + 'vw'
      }
    },
    props: ['projects', 'titleName'],
    data () {
      return {
        amount: 0
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .projects
    .content
      background #efefef
      height 700px
      width 100%
    .go
      position absolute
      z-index 999
      height 300px
      width 18%
      text-align center
      margin-top 180px
      transition-duration .3s
      border-radius 15px
      i
        margin 108px auto
        font-size 84px
        line-height 1em
        display block
    .go:hover
      //background rgba(0, 0, 0, 0.3)
      color #E465A5
    .go-left
      left 0
    .go-right
      right 0
    .viewer
      width 100%
      margin auto
      overflow hidden
      padding 100px 0
      position relative
    .scrollpad
      list-style none
      padding 0
      transition-duration .3s
      li
        display inline-block
        width 100vw
        cursor pointer
      .thumbnail
        display block
        max-width 60vw
        margin 0 40% 0 20%
        box-shadow 0 0 15px #ddd

      li > h4
        text-align center
        width 100%
        margin 0 auto
        font-size 32px
      li > p
        text-align center
        width 100%
        margin 0 auto

    .description
      position absolute
      background rgba(0, 0, 0, 0.6)
      font-size 20px
      color #fff
      z-index 99
      width 60vw
      height 400px
      margin 0 40% 0 20vw
      opacity 0
      transition-duration .3s
      overflow hidden
      .container
        margin 30px
        font-weight 200
        text-align left
        h4
          font-size 20px
          font-weight 400
          margin 0
          margin-top 20px
        p
          font-size 18px
          margin 0
    .description:hover
      opacity 1
    .banner
      max-height 40px
      margin-top 20px
    .middle-banner
      width 100%
    .start-banner
      padding-left 48.5%
      width 51.5%
    .end-banner
      padding-right 48.5%
      width 51.5%
</style>
