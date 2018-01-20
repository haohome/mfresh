<template>
<div>
  <Mf-header/>
  <nav class="navbar">
  <div class="container">
    <div class="nav">
      <ul>
        <li><a href="#"><span class="icon_home"></span>首页</a></li>
        <li><a href="about.html">关于净美仕</a></li>
        <li><a href="news.html">公司动态</a></li>
        <li class="nav_pd">
          <a href="product.html">产品中心<span class="icon_pd"></span></a>
          <div class="pd_dropdown">
            <a href="product.html?type=1">净美仕净化器</a>
            <a href="product.html?type=2">净美仕滤网</a>
          </div>
        </li>
        <li><a href="contact.html">联系我们</a></li>
      </ul>
    </div>
    <div class="s_cart">
      <a href="cart.html">
        <span class="icon_cart"></span>购物车(<strong id="cart_sum">0</strong>)<span class="icon_sj"></span>
      </a>
      <div class="cart_dropdown">
        <!--<h3>您的购物车为空~</h3>-->
        <ul>
          <!-- <li>-->
            <!--<a href=""><img src="product-imgs/jhq-m8088a.jpg" alt=""/></a>-->
            <!--<div>-->
              <!--<span>-</span><input type="text" value="2"/><span>+</span>-->
            <!--</div>-->
            <!--<strong>¥1599.00</strong>-->
            <!--<em></em>-->
          <!--</li>-->
          <!--<li>-->
            <!--<a href=""><img src="product-imgs/jhq-m8088a.jpg" alt=""/></a>-->
            <!--<div>-->
              <!--<span>-</span><input type="text" value="2"/><span>+</span>-->
            <!--</div>-->
            <!--<strong>¥1599.00</strong>-->
            <!--<em></em>-->
          <!--</li> -->
        </ul>
        <div class="cd_js clearfloat">
          <span>共计：<strong>0.00</strong></span>
          <a href="#">结算</a>
        </div>
      </div>
    </div>
  </div>
</nav>
<!--banner-->
<div class="banner">
  <!-- 练习：编写banner的html和css-->
  <!-- 图片列表-->
  <ul>
    <li style="background: url(images/banner_01.jpg) center 0 no-repeat; display: block;z-index: 20;"><a href="#" class="link"></a></li>
    <li style="background: url(images/banner_02.jpg) center 0 no-repeat;"><a href="#" class="link"></a></li>
    <li style="background: url(images/banner_03.jpg) center 0 no-repeat;"><a href="#" class="link"></a></li>
    <li style="background: url(images/banner_04.jpg) center 0 no-repeat;"><a href="#" class="link"></a></li>
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
    <h2 class="title"><a href="#" class="more">more</a>净美仕产品</h2>
    <ul class="clearfloat">
      <li><a href="#" class="link"><img src="images/01.jpg" alt=""/></a></li>
      <li><a href="#" class="link"><img src="images/02.jpg" alt=""/></a></li>
      <li><a href="#" class="link"><img src="images/03.jpg" alt=""/></a></li>
    </ul>
  </div>
  <div class="ind_con2 clearfloat">
    <div class="ind_about">
      <h2 class="title"><a href="#" class="more">more</a>关于净美仕</h2>
      <p>北京净美仕环境科技有限公司自诞生起一直关注人类呼吸健康的问题，并专注于室内空气质量的研究与改善。2003年，非典来袭，环境安全威胁到了每个人的生命，全国陷入一片恐慌。净美仕肩负着为人类创造健康安全生活环境的使命应运而生。2012年7月，亿朗以“净美仕(Mfresh)”为品牌重塑，以崭新的面貌屹立在净化行业。 <a
        href="#">查看更多</a></p>
    </div>
    <div class="ind_news">
      <h2 class="title"><a href="#" class="more">more</a>公司动态</h2>
      <ul>
        <li><span>2016-02-21</span><a href="">空气净化器要逆天？ “玫瑰金”“土豪金”齐上阵</a></li>
        <li><span>2016-02-21</span><a href="">净美仕新风净化系统 助力校园新风行动</a></li>
        <li><span>2016-02-21</span><a href="">全国新风行动全面启动 助推净美仕战略升级</a></li>
        <li><span>2016-02-21</span><a href="">智能空气净化器翻盘：净美仕能否领衔?</a></li>
      </ul>
    </div>
  </div>
</div>
<footer class="footer">
  <Mf-footer/>
</footer>
</div>
</template>
<script>
import Header from './common/Header'
import Footer from './common/Footer'
export default {
  name: 'Index',
  data () {
    return {
    }
  },
  components: {
    'Mf-header': Header,
    'Mf-footer': Footer
  }
}
</script>

<style>
</style>
