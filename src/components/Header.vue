<template>
  <div>
   
    <header class="header container">
      <h1 class="logo">
        <a href="index.html" class="link"></a>
      </h1>
      <div class="h_con">
        <ul class="clearfloat">
          <li class="phone">4000-585-116</li>
          <li>
            <a href="#">中文</a>
          </li>
          <li>
            <em>|</em>
          </li>
          <li>
            <a href="#">English</a>
          </li>
          <li>
            <a href="#" class="weixin"></a>
          </li>
          <li>
            <a href="#" class="weibo"></a>
          </li>
          <li v-show="!isLogin">
            <a href="login.html" class="h_login">登录</a>
          </li>
          <li>
            <em>|</em>
          </li>
          <li v-show="!isLogin">
            <router-link to="/register" class="h_register">注册</router-link>
          </li>
          <li class="top_user" v-show="isLogin">
            <a href>{{uname}}</a>
          </li>
          <li class="top_quit" v-show="isLogin">
            <a href>退出</a>
          </li>
        </ul>
        <div class="search clearfloat">
          <button type="button"></button>
          <input type="text" />
        </div>
      </div>
    </header>
    <!--nav-->
    <nav class="navbar">
      <div class="container">
        <div class="nav">
          <ul>
            <li>
              <router-link to="/">
                <span class="icon_home"></span>首页
              </router-link>
            </li>
            <li>
              <router-link to="/about">关于净美仕</router-link>
            </li>
            <li>
              <router-link to="/news">公司动态</router-link>
            </li>
            <li class="nav_pd">
              <a href="product.html">
                产品中心
                <span class="icon_pd"></span>
              </a>
              <div class="pd_dropdown">
                <a href="product.html?type=1">净美仕净化器</a>
                <a href="product.html?type=2">净美仕滤网</a>
              </div>
            </li>
            <li>
              <a href="contact.html">联系我们</a>
            </li>
          </ul>
        </div>
        <div class="s_cart">
          <a href="cart.html">
            <span class="icon_cart"></span>购物车(
            <strong id="cart_sum">0</strong>)
            <span class="icon_sj"></span>
          </a>
          <div class="cart_dropdown">
            <!--<h3>您的购物车为空~</h3>-->
            <ul>
              <!--<li>-->
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
              <!--</li>-->
            </ul>
            <div class="cd_js clearfloat">
              <span>
                共计：
                <strong>0.00</strong>
              </span>
              <a href="#">结算</a>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  
  name: "Header",
  data() {
    return {
      isLogin: false,
      uname: ""
    };
  },
  mounted() {
    
    this.isLogin = sessionStorage.uname != undefined;
    this.uname = sessionStorage.uname;
  },
  
  watch: {
    $route: function() {
      this.isLogin = sessionStorage.uname != undefined;
      this.uname = sessionStorage.uname;
    }
  }
};
</script>

<style></style>
