<template>
<div class="icons">
  <swiper>
    <swiper-slide v-for="(page,index) of pages" :key="pages">
     <div class="icon"  v-for="item of page" :key="item.id">
      <div class="icon-img">
        <img :src="item.imgUrl"
              class="icon-img-content"/>
      </div>
    <p class="icon-desc">{{item.desc}}</p>
  </div>
    </swiper-slide>
  </swiper>

</div>

</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList:[
        {
          id:'0001',
          imgUrl:require('../../../assets/img/icon1.png'),
          desc:'景点门票'
        },
        {
          id:'0002',
          imgUrl:require('../../../assets/img/icon2.png'),
          desc:'海洋馆'
        },
        {
          id:'0003',
          imgUrl:require('../../../assets/img/icon3.png'),
          desc:'游乐场'
        },
        {
          id:'0004',
          imgUrl:require('../../../assets/img/icon4.png'),
          desc:'泡温泉'
        },
        {
          id:'0005',
          imgUrl:require('../../../assets/img/icon5.png'),
          desc:'一日游'
        },
        {
          id:'0006',
          imgUrl:require('../../../assets/img/icon6.png'),
          desc:'精品小团'
        },
        {
          id:'0007',
          imgUrl:require('../../../assets/img/icon7.png'),
          desc:'武夷山'
        },
        {
          id:'0008',
          imgUrl:require('../../../assets/img/icon8.png'),
          desc:'踏青赏花'
        },
        {
          id:'0009',
          imgUrl:require('../../../assets/img/icon9.png'),
          desc:'玩转贵安'
        }
        ,
        {
          id:'0010',
          imgUrl:require('../../../assets/img/icon10.png'),
          desc:'城市观光'
        }
      ]
    }
  },
  computed:{
      pages(){
          const pages = []
          this.iconList.forEach((item,index)=>{
                const page = Math.floor(index/8)
                if(!pages[page]){
                  pages[page]=[]
                }
            pages[page].push(item)
          })
        return pages
      }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
    .icons >>> .swiper-container
      height: 0
      padding-bottom: 50%
      .icon
        position:relative
        overflow: hidden
        float: left
        width: 25%//宽25%
        height:0
        padding-bottom: 25%//高也25%
        .icon-img
         position: absolute
         top: 0
         left: 0
         right: 0
         bottom: .44rem
         box-sizing border-box
         padding .1rem
        .icon-img-content
          display:block
          margin:0 auto
          height:100%
        .icon-desc
          position: absolute
          left: 0
          right: 0
          bottom:0
          height: .44rem
          line-height: .44rem
          text-align:center
          color:$darkTextColor
          ellipse()


</style>
