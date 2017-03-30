<template>
  <div class="projects">
    <subtitle title="项目经历"></subtitle>
    <div class="content" on>
      <div class="go go-left" @click="amount--" v-show="amount!=0"><p><<</p></div>
      <div class="go go-right" @click="amount++" v-show="amount!=projects.length-1"><p>))</p></div>
      <div class="viewer">
        <ul class="scrollpad" :style="getStyle">
          <li v-for="(project, index) in projects" :id="'project'+ (index+1)" @click="newTab(project.link)">
            <div class="description">
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
  import thumbnail from '../thumbnail/thumbnail'
  export default {
    components: {
      subtitle,
      thumbnail
    },
    methods: {
      newTab: function (link) {
        if (link.isEmpty()) return
        window.open(link)
      }
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
            link: 'http://baidu.com',
            description: [
              {
                title: '项目时间',
                content: '次少系飞志根感资元，方列容划派场验，战水弦果派业I。 由完三流立争色美心，题南水对着养单建为想，她究隶委这思利蹦。 员头工白切张万，此照备被派，分G红目霸。'
              },
              {
                title: '公都本料实',
                content: '将制片机等养目大小次，切品时定想完通精第，增里隶制，向记须查离的标连Y串度租束往求例。'
              },
              {
                title: '白安需相结',
                content: '与民究严示农才题知近安应开，做在 只什素把次千，报采验厂备次数很，B适做总选这离。 又金术争标亲示然社西里样，高北攻有长8法。'
              }
            ],
            img: 'gocheer.jpg'
          },
          {
            name: '枸杞GoCheer',
            from: '2016.10',
            to: '2016.12',
            link: 'http://baidu.com',
            description: [
              {
                title: '项目时间',
                content: '次少系飞志根感资元，方列容划派场验，战思利蹦。 员头工白切张万，此照备被派，分G红目霸。'
              },
              {
                title: '公都本料实',
                content: '将制片机等养目大小次，切品时定想完通精第，增里隶制八2织走。 于置县展响商象过，价派县思育劳出，还情详般线秧型。 因存其法育划么到子方火空六及道质严，向记须查离的标连Y串度租束往求例。'
              },
              {
                title: '白安需相结',
                content: '与民究严示农才题知数很，B适做总选这离。 又金术争标亲示然社西里样，高北严全子上光只斯长分各，改价M则奔攻有长8法。'
              }
            ],
            img: 'gocheer.jpg'
          },
          {
            name: '枸杞GoCheer',
            from: '2016.10',
            to: '2016.12',
            link: 'http://baidu.com',
            description: [
              {
                title: '项目时间',
                content: '次少系为想，她究隶委这思利蹦。 员头工白切张万，此照备被派，分G红目霸。'
              },
              {
                title: '公都本料实',
                content: '将制片机等养目大小次，切品时定想完通精第，增里隶制八2织走。 于置县展响到子方火空六及道质严，向记须查离的标连Y串度租束往求例。'
              },
              {
                title: '白安需相结',
                content: '与民究严示农才题知近安应开，千，报采验厂备次数很，B适做总选这离。 又金术争标亲示然社西里样，高北严全子上光只斯长分各，改价M则奔攻有长8法。'
              }
            ],
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
      position relative
    .scrollpad
      list-style none
      padding 0
      transition-duration .3s
      li
        display inline-block
        width 99vw
        cursor pointer
      .thumbnail
        display block
        max-width 60%
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
      width 60%
      height 400px
      margin 0 40% 0 20%
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
