<template>
  <div id="app">
    <v-header></v-header>
    <overview :titleName="titles.overview" :introduction="resume.introduction" :eduinfo="resume.edu"></overview>
    <project :titleName="titles.project" :projects="resume.projects"></project>
    <skill :titleName="titles.skill" :skills="resume.skills" :keys="resume.keys"></skill>
    <info :titleName="titles.info" :github="resume.github" :email="resume.email" :blog="resume.blog"></info>
  </div>
</template>

<script>
  import header from './components/header/header'
  import overview from './components/overview/overview'
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
      'skill': skill
    },
    computed: {
      titles: function () {
        return this.subtitles[this.language]
      }
    },
    data () {
      return {
        resume: {},
        language: 'en',
        subtitles: {
          'zh-CN': {
            overview: '个人简介',
            project: '项目经历',
            skill: '专业技能',
            info: '了解更多'
          },
          en: {
            overview: 'Overview',
            project: 'Projects',
            skill: 'Skills',
            info: 'Contact Me'
          }
        }
      }
    },
    created: function () {
      this.$http.get('static/resume-zh-CN.json').then(resp => {
        this.resume = resp.body
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
</style>
