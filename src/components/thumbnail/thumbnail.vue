<template>
  <div class="thumbnail" :style="styleObj">
    <img :src="imgSrc" :alt="alt"/>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: ['imgSrc', 'alt', 'width', 'height'],
    data () {
      return {
        styleObj: {
          width: this.width,
          height: this.height
        }
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
.thumbnail img
  max-width 100%
  max-height 100%
</style>
