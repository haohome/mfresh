<template>
<div>
<!--banner-->
<div class="banner">
  <!-- 练习：编写banner的html和css-->
  <!-- 图片列表-->
  <ul>
    <li v-for="(temp,key) in bannerList" :key=key  :style='"background: url("+require("../assets/"+temp.pic)+") center 0 no-repeat; display: block;z-index: 20;"'><a href="#" class="link"></a></li>
  </ul>
  <!-- 左右箭头-->
  <span class="cut prev"></span>
  <span class="cut next"></span>
  <!-- 小圆点指示器-->
  <div class="indicator">
    <a href="" class="cur"></a><a href=""></a><a href=""></a><a href=""></a>
  </div>
</div>
<!--main-->
<div class="main container">
  <div class="ind_con1">
    <h2 class="title"><a href="#" class="more">more</a>JMS产品</h2>
    <ul class="clearfloat">
      <li><a href="#" class="link"><img src="../assets/images/01.jpg" alt=""/></a></li>
      <li><a href="#" class="link"><img src="../assets/images/02.jpg" alt=""/></a></li>
      <li><a href="#" class="link"><img src="../assets/images/03.jpg" alt=""/></a></li>
    </ul>
  </div>
  <div class="ind_con2 clearfloat">
    <div class="ind_about">
      <h2 class="title"><a href="#" class="more">more</a>关于JMS</h2>
      <p>北京JMS环境科技有限公司自诞生起一直关注人类呼吸健康的问题，并专注于室内空气质量的研究与改善。2003年，非典来袭，环境安全威胁到了每个人的生命，全国陷入一片恐慌。JMS肩负着为人类创造健康安全生活环境的使命应运而生。2012年7月，亿朗以“JMS(Mfresh)”为品牌重塑，以崭新的面貌屹立在净化行业。 <a
        href="#">查看更多</a></p>
    </div>
    <div class="ind_news">
      <h2 class="title"><a href="#" class="more">more</a>公司动态</h2>
      <ul>
        <li><span>2016-02-21</span><a href="">空气净化器要逆天？ “玫瑰金”“土豪金”齐上阵</a></li>
        <li><span>2016-02-21</span><a href="">JMS新风净化系统 助力校园新风行动</a></li>
        <li><span>2016-02-21</span><a href="">全国新风行动全面启动 助推JMS战略升级</a></li>
        <li><span>2016-02-21</span><a href="">智能空气净化器翻盘：JMS能否领衔?</a></li>
      </ul>
    </div>
  </div>
</div>

</div>
</template>
<script>
export default {
  name: 'Index',
  data () {
    return {
      bannerList:[]
    }
  },
  mounted(){
    this.getCarosel()
  },
  methods:{
    //获取轮播图背景图片
    getCarosel(){
      var self=this;
      self.$axios.get('http://127.0.0.1:3000/carosel/product')
      .then(function (response) {
      self.bannerList=response.data;
      
      })
      .catch(function (error) {
        console.log(error);
      });
    }
  }
}
</script>

<style>
</style>
