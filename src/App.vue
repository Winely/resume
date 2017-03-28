<template>
  <div id="app">
    <v-header></v-header>
    <overview></overview>
    <project></project>
    <skill></skill>
    <info></info>
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
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import url(//fonts.googleapis.com/earlyaccess/notosanssc.css);
  @import url(//fonts.googleapis.com/css?family=Noto+Sans);
  body
    margin 0
    font-family "Noto Sans","Noto Sans SC",sans-serif
  .container
    margin 20px 10%
</style>
