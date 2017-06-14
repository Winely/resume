<template>
  <div class="projects">
    <subtitle :titleName="titleName" id="subtitle-project"></subtitle>
    <ul class="container">
      <li v-for="(project, index) in projects" :id="'project'+ (index+1)">
        <div class="shortcut" @click="newTab(project.link)">
          <thumbnail :imgSrc="'./static/'+project.img" width="200px" height="150px"></thumbnail>
          <span class="date">{{project.from}} ~ {{project.to}}</span>
        </div>
        <!--<div class="divider"></div>-->
        <div class="project-info">
          <h4 @click="newTab(project.link)">{{project.name}}</h4>
          <div v-for="item in project.description" class="description">
            <h5>{{item.title}}</h5>
            <p>{{item.content}}</p>
          </div>
        </div>
      </li>
    </ul>
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
    props: ['projects', 'titleName'],
    data () {
      return {
        amount: 0
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .container
    list-style none
    li
      display flex
      align-items center
      margin-bottom 40px
  .shortcut
    flex 2
    display flex
    flex-direction column
    align-items center
    img
      box-shadow 0 0 14px #aaa
      cursor pointer
  .divider
    flex-shrink 1
    height: 30px
    width: 30px
    background #d8d96b
    border-radius 99em
    margin 30px

  .project-info
    flex 7
    padding-left 40px
    h4
      font-size 24px
      margin 5px
      cursor pointer
    h5,p
      font-size 16px
      margin 5px
      color #888
</style>
