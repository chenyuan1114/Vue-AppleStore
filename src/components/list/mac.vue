<template>
<div>
  <div class="wrapper">
    <ul class="content">
      <li v-for="(item,index) in headerImg" :key="index" class="img_box">
        <img :src="item.img" class="img">
        <div class="name">{{item.name}}</div>
      </li>
    </ul>
  </div>
  <div class="wrapper">
    <ul >
      <li v-for="(item,index) in descFirst" :key="index">
        <h2 class="desc_one">{{item.desc_one}}</h2>
        <h3 class="desc_two">{{item.desc_two}}</h3>
        <div class="desc_three">{{item.desc_three}}</div>
        <img class="mac_Img" :src="item.mac_Img">
      </li>
    </ul>   
  </div>
  <!-- <div class="wrapper bgc_img">
    <ul>
      <li v-for="(item,index) in descSecond" :key="index">       
        <h2 class="descsecond_one">{{item.descsecond_one}}</h2>
        <h3 class="descsecond_two">{{item.descsecond_two}}</h3>
        <div class="descsecond_three">{{item.descsecond_three}}</div>
        <img class="descsecond_img" :src="item.descsecond_img">
      </li>
    </ul>   
  </div> -->
  <div class="footer">
    <div class="desc">* 实际折抵金额取决于设备的状况、配置及制造年份。年满 18 周岁及以上者才能享受此项折抵换购服务。并非所有设备都符合折抵换购条件。Apple 的折抵服务合作伙伴将提供关于符合条件设备的折抵与回收的更多信息。可能需要遵循限定条款和条件。所支付金额基于所收到的设备状况与在估算折抵金额时你所提供的描述是否相符。Apple 保留出于任何原因拒绝或限制任何设备 (及其数量) 的权利。在 Apple Store 零售店：该服务需出示政府颁发并附有照片的有效身份证件 (当地法律可能会要求存储该信息)。现有设备的折抵金额可用于冲抵购买新的 Apple 设备。该服务可能仅在部分零售店提供。部分 Apple Store 零售店可能会有附加条件。</div>
    <div class="desc">** iCloud 在中国内地由云上贵州大数据产业发展有限公司运营。</div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Mac',
  data () {
    return {
      headerImg: [],
      descFirst: [],
      descSecond: []
    }
  },
  created () {
    this.$http.get('https://www.easy-mock.com/mock/5d247619ff529b110e5ccf69/Apple-Store/Mac')
      .then(res => {
        console.log(res)
        this.headerImg = res.data.data.headerImg,
        this.descFirst = res.data.data.descFirst,
        this.descSecond = res.data.data.descSecond
      })
  }
}
</script>

<style lang="stylus" scoped>
.wrapper
  background-color #fafafa
  border-bottom 20px solid #ffffff
  &.first-child
    border none
  .content
    white-space nowrap
    width 100%
    height 120px
    overflow scroll
    background-color #f1f1f1
    .img_box
      display inline-block
      list-style none    
      margin-top 25px
      .img
        width 50px
        height 50px
        margin 0 20px
      .name
        font-size 12px
        text-align center
  .desc_one
    padding-top 55px
    text-align center
    font-weight 500
  .desc_two
    text-align center
    font-size 35px
    line-height 1.1
    font-weight 550
    margin-top 10px
  .desc_three
    text-align center
    color #0070c9
    font-size 18px
    letter-spacing .011em
    margin-top 20px
    margin-bottom 40px
  .mac_Img
    width 310px
    height 230px
    margin-left 32px
// .bgc_img
//   width 375px
//   height 445px
//   background-image url('https://www.apple.com/v/mac/home/ah/images/overview/macos/mojave__emq4cjg0jhea_small_2x.jpg')
//   .descsecond_one
//     padding-top 55px
//     text-align center
//     margin 0 40px
//     font-weight 550
//     font-size 30px
//   .descsecond_two
//     text-align center
//     text-align center
//     margin 20px 45px
//     font-weight normal
//     font-size 16px
//   .descsecond_three
//     text-align center
//     color #0070c9
//     font-size 18px
//     letter-spacing .011em
//     margin-top 20px
//     margin-bottom 40px
  // .descsecond_img
  //   width 310px
  //   height 190px
  //   margin-left 32px
.footer
  width 100%
  background-color #f4f3f3
  .desc
    font-size 12px
    line-height 1.33341
    font-weight 400   
    color #888
    margin 0 10px
    padding-top 10px
</style>
