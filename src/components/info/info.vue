<template>
  <div class="info">
    <subtitle :titleName="titleName" id="subtitle-info"></subtitle>
    <div class="container">
      <div v-if="blog" class="blog">
        <a :href="blog.protocol+'://'+blog.url" target="_blank">
          <i class="iconfont icon-iconblog2"></i>
          {{blog.url}}
        </a>
      </div>
      <div v-if="github" class="github">
        <a :href="github.protocol+'://'+github.url" target="_blank">
          <i class="iconfont icon-github"></i>
          {{github.url}}
        </a>
      </div>
      <div v-if="email" class="email">
        <a :href="'mailto:'+email" target="_blank">
          <i class="iconfont icon-email"></i>
          {{email}}
        </a>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  export default {
    props: ['github', 'blog', 'email', 'titleName'],
    components: {
      subtitle
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
.info
  .container
    display flex
    justify-content space-around
  i
    color #EEC057
    font-size larger
  a
    text-decoration none
    color #000
    font-size 18px

</style>
