<template>
  <div id="app">
    <v-header :name="resume.name" :slogan="resume.slogan" :email="resume.email"></v-header>
    <div class="lang-opt">
      <input type="radio" id="lang-zh-CN" name="lang" v-model="language" value="zh-CN"/>
      <label for="lang-zh-CN">中</label>
      <input type="radio" id="lang-en" name="lang" v-model="language" value="En"/>
      <label for="lang-en">En</label>
    </div>
    <overview :titleName="titles.overview" :introduction="resume.introduction"></overview>
    <edu :titleName="titles.edu" :eduinfo="resume.edu"></edu>
    <project :titleName="titles.project" :projects="resume.projects"></project>
    <skill :titleName="titles.skill" :skills="resume.skills" :keys="resume.keys"></skill>
    <info :titleName="titles.info" :github="resume.github" :email="resume.email" :blog="resume.blog"></info>
  </div>
</template>

<script>
  import header from './components/header/header'
  import overview from './components/overview/overview'
  import edu from './components/edu/edu'
  import project from './components/project/project'
  import skill from './components/skill/skill'
  import info from './components/info/info'
  export default {
    name: 'app',
    components: {
      'v-header': header,
      'overview': overview,
      'project': project,
      'info': info,
      'skill': skill,
      edu
    },
    computed: {
      titles: function () {
        return this.subtitles[this.language]
      }
    },
    watch: {
      language: function (val) {
        this.$http.get('static/resume-' + val + '.json').then(resp => {
          console.log(val)
          this.resume = resp.body
          document.title = resp.body.name + '\'s Resume'
        })
      }
    },
    data () {
      return {
        resume: {},
        language: 'zh-CN',
        subtitles: {
          'zh-CN': {
            overview: '个人简介',
            edu: '教育经历',
            project: '项目经历',
            skill: '专业技能',
            info: '了解更多'
          },
          'En': {
            overview: 'Overview',
            edu: 'Education',
            project: 'Projects',
            skill: 'Skills',
            info: 'Contact Me'
          }
        }
      }
    },
    created: function () {
      this.$http.get('static/resume-' + this.language + '.json').then(resp => {
        this.resume = resp.body
        document.title = resp.body.name + '\'s Resume'
      })
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import url(//fonts.googleapis.com/earlyaccess/notosanssc.css);
  body
    margin 0
    font-family "Noto Sans SC", sans-serif

  .container
    margin 20px 10%

  .lang-opt
    position fixed
    z-index 99
    right 30px
    top 16px
    [type=radio]
      display none
    input[type=radio]:checked + label
      background #EEC057
    label
      background rgba(192, 240, 235, 0.2)
      color #ffffff
      border-radius 5px
      padding 0.1em 0.4em
      transition-duration .3s
    label:hover
      background #EEC057

</style>
