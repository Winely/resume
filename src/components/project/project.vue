<template>
  <div class="projects">
    <subtitle title="项目经历"></subtitle>
    <div class="content">
      <div class="go go-left" @click="amount--" v-show="amount!=0"><p><<</p></div>
      <div class="go go-right" @click="amount++" v-show="amount!=projects.length-1"><p>))</p></div>
      <div class="viewer">
        <ul class="scrollpad" :style="getStyle">
          <li v-for="(project, index) in projects" :id="'project'+ (index+1)">
            <img :src="'./static/'+project.img"/>
            <svg v-if="index===0" class="banner start-banner">
              <use xlink:href="#banner-start"></use>
            </svg>
            <svg v-else-if="index<projects.length-1" class="banner middle-banner">
              <use xlink:href="#banner-middle"></use>
            </svg>
            <svg v-else class="banner end-banner">
              <use xlink:href="#banner-end"></use>
            </svg>
            <h4>{{project.name}}</h4>
            <p>{{project.from}} ~ {{project.to}}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  export default {
    components: {
      subtitle
    },
    computed: {
      getStyle: function () {
        return 'margin-left: -' + this.amount * 100 + '%; width:' + this.projects.length * 100 + 'vw'
      }
    },
    data () {
      return {
        amount: 0,
        projects: [
          {
            name: '枸杞GoCheer',
            from: '2016.10',
            to: '2016.12',
            description: 'dfadfjweifkneewufbiujndoaiieoerqwre',
            img: 'gocheer.jpg'
          },
          {
            name: '枸杞GoCheer',
            from: '2016.10',
            to: '2016.12',
            description: 'dfadfjweifkneewufbiujndoaiieoerqwre',
            img: 'gocheer.jpg'
          },
          {
            name: '枸杞GoCheer',
            from: '2016.10',
            to: '2016.12',
            description: 'dfadfjweifkneewufbiujndoaiieoerqwre',
            img: 'gocheer.jpg'
          }
        ]
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
      height 100px
      width 15%
      text-align center
      margin-top 250px
      p
        margin 35px auto
    .go:hover
      background rgba(0, 0, 0, 0.3)
    .go-left
      left 0
    .go-right
      right 0
    .viewer
      width 100%
      margin auto
      overflow hidden
      padding 100px 0
    .scrollpad
      list-style none
      padding 0
      transition-duration .3s
      li
        display inline-block
        width 99vw
      img
        display block
        max-width 60%
        margin 0 40% 0 20%
        box-shadow 0 0 15px #ddd
      h4
        text-align center
        width 100%
        margin 0 auto
        font-size 32px
      p
        text-align center
        width 100%
        margin 0 auto

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
