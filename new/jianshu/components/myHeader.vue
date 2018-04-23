<template>
    <div>
        <nav class="navbar navbar-fixed-top">
            <div class="width-limit">
                <!--logo-->
                <nuxt-link class="logo" to="/">
                    <img src="~/assets/img/nav-logo.png">
                </nuxt-link>
                <!--右上角，写文章-->
                <nuxt-link to="/write" class="write-btn">
                    <i class="fa fa-edit"></i>
                    写文章
                </nuxt-link>
                <!--登录用户信息-->
                <div class="user" v-on:mouseenter="show=true" v-on:mouseleave="show=false">
                    <div class="drop-down">
                        <nuxt-link to="/u/123" class="avatar">
                            <img src="~/assets/img/aa.jpg">
                        </nuxt-link>
                    </div>
                    <ul class="drop-menu" v-show="show">
                       <li>
                           <nuxt-link to="/">
                               <i class="fa fa-home"></i>
                               我的主页
                           </nuxt-link>
                       </li>
                        <li>
                            <nuxt-link to="/user/123/like">
                                <i class="fa fa-heart"></i>
                                喜欢的文章
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/bookmarks">
                                <i class="fa fa-bookmark"></i>
                                收藏的文章
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/settings/basic">
                                <i class="fa fa-cog"></i>
                                设置
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/logout">
                                <i class="fa fa-sign-out"></i>
                                退出
                            </nuxt-link>
                        </li>
                    </ul>
                </div>
                <!--右上角，登录和注册-->
                <!-- 导航部分 -->
                <div class="container" style="height:56px">
                  <transition enter-active-class="animated fadeInDown" leave-active-class="animated fadeOutUp">
                    <ul class="nav-list" v-show="f">
                        <li>
                            <nuxt-link to="/" class="active">
                                <i class="fa fa-compass"></i>
                                <span>发现</span>
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/">
                                <i class="fa fa-book"></i>
                                <span>关注</span>
                            </nuxt-link>
                        </li>
                        <li class="user" @mouseover="a=true" @mouseleave="a=false">
                            <nuxt-link to="/notify">
                                <i class="fa fa-bell-o"></i>
                                <span>消息</span>
                            </nuxt-link>
                            <ul class="drop-menu" v-show="a">
                                <li>
                                    <nuxt-link to="/">
                                        <i class="fa fa-comment-o"></i>
                                        评论
                                    </nuxt-link>
                                </li>
                                <li>
                                    <nuxt-link to="/">
                                        <i class="fa fa-envelope-o"></i>
                                        简信
                                    </nuxt-link>
                                </li>
                                <li>
                                    <nuxt-link to="/">
                                        <i class="fa fa-square-o"></i>
                                        关注
                                    </nuxt-link>
                                </li>
                                <li>
                                    <nuxt-link to="/">
                                        <i class="fa fa-heart-o"></i>
                                        喜欢和赞
                                    </nuxt-link>
                                </li>
                            </ul>
                        </li>
                        <li class="search">
                            <form method="post">
                                <input type="text" placeholder="搜索" class="search-input">
                                <a href="#" class="search-btn">
                                    <i class="fa fa-search"></i>
                                </a>
                            </form>
                        </li>
                    </ul>
                    </transition>
                    <div class="nav-mune" v-on:click="f=!f">
                        <ul class="ul-mune">
                            <li></li>
                            <li></li>
                            <li></li>
                        </ul>
                    </div>
                </div>
            </div>
            <!-- <ul class="ul-li" v-show="c">
                <li class="active">
                    <nuxt-link to="/" > 
                    <i class="fa fa-compass"></i>
                        <span>发现</span>
                    </nuxt-link>
                </li>
                <li>
                    <nuxt-link to="/">
                    <i class="fa fa-book"></i>
                        <span>关注</span>
                    </nuxt-link>
                </li>
                <li class="aaa" @mouseover="b=true,d=false" @mouseleave="b=false,d=true">
                    <nuxt-link to="/">
                    <i class="fa fa-bell-o"></i>
                        <span>消息</span>
                    </nuxt-link>
                    <ul class="drop-menu" v-show="b">
                        <li>
                            <nuxt-link to="/">
                                <i class="fa fa-comment-o"></i>
                                评论
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/">
                                <i class="fa fa-envelope-o"></i>
                                简信
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/">
                                <i class="fa fa-square-o"></i>
                                关注
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/">
                                <i class="fa fa-heart-o"></i>
                                喜欢和赞
                            </nuxt-link>
                        </li>
                    </ul>
                </li>
                <li class="search" v-show="d">
                    <form method="post">
                        <input type="text" placeholder="搜索" class="search-input">
                        <a href="#" class="search-btn">
                            <i class="fa fa-search"></i>
                        </a>
                    </form>
                </li>
            </ul> -->
        </nav>
    </div>
</template>
<script>
import $ from "jquery";
export default {
  name: "myHeader",
  data() {
    return {
      show: false,
      a: false,
      b: false,
      f: false
    };
  }
};
</script>
<style scoped>
nav {
  width: 100%;
  height: 56px;
}
.navbar {
  margin-bottom: 20px;
  border-bottom: 1px solid #f0f0f0;
  background-color: #fff;
}
.navbar:before {
  content: "";
  display: table;
}
.container {
  position: relative;
}
.navbar-fixed-top {
  position: fixed;
  left: 0;
  top: 0;
  z-index: 9999;
}
nav .width-limit {
  min-width: 768px;
  max-width: 1440px;
  margin: 0 auto;
}
nav .logo {
  float: left;
  height: 56px;
  display: block;
}
nav .logo img {
  height: 100%;
}
nav .write-btn {
  float: right;
  width: 100px;
  height: 40px;
  line-height: 40px;
  margin: 8px 15px 0;
  border-radius: 20px;
  font-size: 15px;
  color: #fff;
  background: #ea6f5a;
  text-align: center;
}
nav .wirte-btn:hover {
  background: #ec6149;
}
nav .user {
  position: relative;
  float: right;
  z-index: 9999;
}
nav .user .avatar {
  position: relative;
  display: block;
  width: 40px;
  height: 40px;
  margin: 8px 28px 8px 20px;
}
nav .user:hover {
  background-color: #f5f5f5;
}
nav .user .avatar:before {
  content: "";
  position: absolute;
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: 5px solid #999;
  top: 18px;
  right: -14px;
}
nav .user .avatar img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 1px solid #eee;
}
nav .user .drop-menu {
  position: absolute;
  left: 0;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
  min-width: 160px;
  z-index: 999;
  margin: 0;
}
nav .user .drop-menu li {
  padding: 10px 20px;
  display: block;
}
nav .user .drop-menu li:hover {
  background-color: #f5f5f5;
}
nav .user .drop-menu li a i {
  margin-right: 10px;
  color: #ea6f5a;
  width: 20px;
  height: 20px;
  font-size: 20px;
  display: inline-block;
}
nav .nav-list {
  float: left;
  margin: 0;
  transition: height 0.5s;
  overflow: hidden;
}
nav .nav-list:after {
  content: "";
  height: 0;
  display: block;
  visibility: hidden;
  clear: both;
}
nav .nav-list > li {
  float: left;
  margin-right: 5px;
}
nav .nav-list > li a {
  display: block;
  height: 56px;
  line-height: 26px;
  padding: 15px;
}
nav .nav-list > li a.active {
  color: #ea6f5a;
  background: none;
}
nav .nav-list > li a:hover {
  background: #f5f5f5;
}
nav .nav-list > li a i {
  margin-right: 5px;
  font-size: 20px;
}
nav .nav-list .search {
  padding-left: 15px;
  margin-right: 10px;
}
nav .nav-list .search form {
  margin-bottom: 20px;
  position: relative;
  top: 9px;
}
nav .nav-list .search form input:focus {
  width: 320px;
}
nav .nav-list .search-input:focus ~ .search-btn {
  background: #969696;
  color: #fff;
  border-radius: 50%;
}
nav .nav-list .search form input {
  height: 38px;
  width: 240px;
  font-size: 14px;
  padding: 0 40px 0 20px;
  background: #eee;
  border: 1px solid #eee;
  border-radius: 40px;
  transition: width 0.5s;
}
nav .nav-list .search form .search-btn {
  position: absolute;
  width: 30px;
  height: 30px;
  top: 4px;
  right: 5px;
  color: #969696;
  text-align: center;
  padding: 0;
}
nav .nav-list .search form .search-btn i {
  display: block !important;
  margin: 0;
  text-align: center;
  line-height: 30px;
  font-size: 15px;
}
nav .nav-list .search form .search-btn:hover {
  background: none;
}

nav .nav-mune {
  padding-top: 15px;
  height: 100%;
  display: none;
}
nav .nav-mune .ul-mune {
  border: 1px solid #999;
  float: left;
  margin: 0;
  border-radius: 5px;
  line-height: 10px;
}

nav .nav-mune .ul-mune li {
  height: 2px;
  width: 30px;
  margin: 5px;
  background-color: #999;
}

@media (max-width: 1440px) {
  nav .nav-list > li a > i {
    display: none;
  }
  nav .nav-list .search form .search-input {
    width: 160px;
  }
  nav .nav-list .search form .search-input:focus {
    width: 240px;
  }
}
@media (max-width: 1080px) {
  nav .nav-list li span {
    display: none;
  }
  nav .nav-list > li a i {
    display: block;
  }
}
@media (min-width: 768px) {
  nav .nav-list {
    display: block !important;
  }
}
@media (max-width: 768px) {
  nav .nav-list {
    position: absolute;
    top: 56px;
    left: 0;
  }
  nav .nav-list {
    width: 100vw;
    margin: 0;
  }
  nav .nav-mune {
    display: block;
  }
  nav .nav-list li {
    width: 100%;
    border-bottom: 1px solid #f0f0f0;
    text-align: center;
    background: #fff;
  }

  nav .nav-list > li a.active:hover {
    background-color: #fff;
  }
  nav .nav-list li .fa {
    display: none;
  }

  nav .nav-list .search {
    padding-left: 15px;
    margin-right: 10px;
  }
  nav .nav-list .search form {
    margin-bottom: 20px;
    position: relative;
    top: 9px;
  }
  nav .nav-list .search-input:focus ~ .search-btn {
    background: #969696;
    color: #fff;
    border-radius: 50%;
  }
  nav .nav-list .search form input {
    height: 38px;
    width: 90% !important;
    font-size: 14px;
    padding: 0 40px 0 20px;
    background: #eee;
    border: 1px solid #eee;
    border-radius: 40px;
    transition: width 0.5s;
  }
  nav .nav-list .search form .search-btn {
    position: absolute;
    width: 30px;
    height: 30px;
    top: 4px;
    right: 6vw;
    color: #969696;
    text-align: center;
    padding: 0;
  }
  nav .nav-list .search form .search-btn i {
    display: block !important;
    margin: 0;
    text-align: center;
    line-height: 30px;
    font-size: 15px;
  }
  nav .nav-list .search form .search-btn:hover {
    background: none;
  }
  nav .nav-list li .drop-menu li a {
    color: #ec6149;
  }
  nav .nav-list .user {
    position: relative;
  }
  nav .nav-list .user ul {
    position: absolute;
    left: 15px;
  }
  nav .nav-list li span {
    display: inline-block;
  }
  nav .nav-list .user ul {
    position: absolute;
    left: 15px;
  }
  nav .nav-list .user ul li {
    background-color: transparent;
  }
  nav .nav-list .user ul {
    display: none;
  }
}
@media (min-width: 768px) {
}
@media (max-width: 356px) {
  nav .nav-list li {
    border-bottom: 0px solid #f0f0f0;
    text-align: left;
    background-color: transparent;
    margin: 0 10px;
  }
  nav .nav-list li .fa {
    display: inline-block;
    width: 15px;
  }
  nav .nav-list > li a.active:hover {
    background-color: transparent;
  }
  nav .nav-list .search .fa {
    display: none;
  }
  nav .nav-list .search form input {
    width: 160px;
    margin: 0;
    float: left;
  }
  nav .nav-list .search form .search-btn {
    display: none;
  }
  nav .nav-list .user ul {
    display: block;
    background-color: transparent;
  }
  nav .nav-list .user ul li {
    background-color: transparent;
  }
  nav .nav-list .user ul li:hover {
    background-color: transparent;
  }
  nav .nav-list .user ul li a:hover {
    background-color: transparent;
  }
}
</style>
