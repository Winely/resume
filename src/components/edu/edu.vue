<template>
  <div id="edu">
    <subtitle :titleName="titleName" id="subtitle-edu"></subtitle>
    <div class="container">
      <div class="edu-item" v-for="item in eduinfo">
        <p class="edu-info">
          <span class="date">{{item.time.from}}~{{item.time.to}} </span>
          <span class="degree">{{item.degree}}</span>
          <span class="point">●</span>
        </p>
        <div class="school-info">
          <p>
            <span class="large-label">{{item.college}}</span>,
            <span class="major">{{item.major}}</span>
          </p>
          <div class="details">
            <p>GPA: {{item.gpa}}/{{item.gpaSum}}, {{item.gpaRank}}</p>
            <p class="award" v-for="award in item.awards">
              <span class="sub-award">{{award.sub}}</span>
              <span class="main-award">{{award.main}}</span>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import subtitle from '../subtitle/subtitle'
  export default {
    props: ['eduinfo', 'titleName'],
    components: {
      subtitle
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  lh = 24px
  .edu-item
    display flex
    align-items baseline
  .edu-info
    vertical-align: middle
    display inline-block
    text-align right
    flex 3

  .school-info
    display inline-block
    flex 7
    p
      margin 10px auto
  pd=50px
  theme=#eec
  .details
    border-left solid 4px theme
    padding-left pd
    margin-left pd*-1
  .point
    color theme
    margin 40px

  .large-label
    font-size lh
    font-weight 600
    margin 0

  .major
    font-size lh

  .degree, .date
    color #555
    text-align: right

  .degree
    margin-left 12px
    font-size 20px
</style>
