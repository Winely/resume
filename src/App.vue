<template>
  <div id="app">
    <v-header></v-header>
    <overview></overview>
    <project></project>
    <info></info>
  </div>
</template>

<script>
  import header from './components/header/header'
  import overview from './components/overview/overview'
  import project from './components/project/project'
  import info from './components/info/info'
  export default {
    name: 'app',
    components: {
      'v-header': header,
      'overview': overview,
      'project': project,
      'info': info
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  body
    margin 0
    font-family "Noto Sans S Chinese",sans-serif
  .container
    margin 20px 10%
</style>
