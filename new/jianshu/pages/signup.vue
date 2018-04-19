<template>
    <div class="sign">
       <div class="sign">
      <!-- logo -->
      <div class="logo">
        <nuxt-link to="/">
          <img src="~/assets/img/logo.png" alt="">
        </nuxt-link>
      </div>
<!-- 主体部分 -->
      <div class="main">
        <!-- title -->
        <div class="title">
          <h4>
            <nuxt-link class="hover" to="/signin">登录</nuxt-link>
           <b>.</b> 
           <nuxt-link class="active" to="/signup">注册</nuxt-link>
            
          </h4>
        </div>
        <!-- form表单 -->
        <div class="js-form">
          <form method="post">
            <div class="input-prepend">
              <input type="text" placeholder="你的昵称">
              <i class="fa fa-user"></i>
            </div>    
            <div class="input-prepend"> 
              <input type="text" placeholder="手机号">
              <i class="fa fa-phone"></i>
            </div>
            <div class="input-prepend ssm"> 
              <input type="text" placeholder="手机验证码">
              <i class="fa fa-shield"></i>
              <a href="#" class="send-ssm">发送验证码</a>
            </div>
            <div class="input-prepend"> 
              <input type="text" placeholder="密码">
              <i class="fa fa-lock"></i>
            </div>
             
            <button class="sign-up-btn">注册</button>
          </form>
          
        </div>
        <!-- 第三方登录 -->
        <div class="more-sign">
          <p class="">社交账户登录</p>
          <ul>
            <li>
              <nuxt-link to="/">
              <i class="fa fa-weixin"></i>
              </nuxt-link>
            </li>
             <li>
              <nuxt-link to="/">
              <i class="fa fa-weibo"></i>
              </nuxt-link>
            </li>
             <li>
              <nuxt-link to="/">
              <i class="fa fa-qq"></i>
              </nuxt-link>
            </li>
            
          </ul>
        </div>
      </div>
    </div>
    </div>
</template>
<script>
export default {
  // 设置页面的标题以及描述、关键字等元信息
  layout: "sign",
  head: {
    title: "注册-简书",
    meta: [
      { charset: "utf-8" },
      { name: "keywords", content: "注册页面" },
      { name: "dscription", content: "注册简书" },
      { name: "author", content: "曹伟豪" }
    ]
  },
  data(){
      return {};
  }
};
</script>