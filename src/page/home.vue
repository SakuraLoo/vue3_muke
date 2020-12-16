<template>
  <div class="pageMax home-page">
    <v-header></v-header>

    <ul class="nav">
      <li v-for="(item,index) in arrList" :key="index">
        <img :src="item.url"/>
        <span> {{ item.name }} </span>
      </li>
    </ul>

    <v-course :courses="courseArr"></v-course>

    <v-footer :tabs="tabsArr"></v-footer>
  </div>
</template>

<script>
import Header from "@/components/header/"
import Course from "@/components/course/"
import Footer from "@/components/footer/"

import webImg from "@/assets/web.png"
import webserviceImg from "@/assets/webservice.png"
import moveImg from "@/assets/move.png"
import dataImg from "@/assets/data.png"
import cloudImg from "@/assets/cloud.png"

import courseImg1 from "@/assets/course1.png"
import courseImg2 from "@/assets/course2.png"
import courseImg3 from "@/assets/course3.png"

// import homeImg from "@/assets/home_active.png"
// import findImg from "@/assets/find.png"
// import downloadImg from "@/assets/download.png"
// import myImg from "@/assets/my.png"

export default {
  components: {
    "v-header": Header,
    "v-course": Course,
    "v-footer": Footer
  },
  data () {
    return {
      arrList: [],

      courseArr: [],

      tabsArr: []
    }
  },
  mounted() {
    this.arrList = [
      {
        url: webImg,
        name: '前端开发'
      },
      {
        url: webserviceImg,
        name: '后端开发'
      },
      {
        url: moveImg,
        name: '移动开发'
      },
      {
        url: dataImg,
        name: '数据库'
      },
      {
        url: cloudImg,
        name: '云计算'
      }
    ],

    this.courseArr = [
      { title: 'Python语言程序设计', msg: '中级·330人在学', img: courseImg1 },
      { title: '自然辩证法概论', msg: '中级·330人在学', img: courseImg2 },
      { title: '大学计算机——计算思维之路CAP', msg: '中级·330人在学', img: courseImg3 },
      { title: 'Python语言程序设计', msg: '中级·330人在学', img: courseImg1 },
      { title: '自然辩证法概论', msg: '中级·330人在学', img: courseImg2 },
      { title: '大学计算机——计算思维之路CAP', msg: '中级·330人在学', img: courseImg3 },
      { title: 'Python语言程序设计', msg: '中级·330人在学', img: courseImg1 },
      { title: '自然辩证法概论', msg: '中级·330人在学', img: courseImg2 },
      { title: '大学计算机——计算思维之路CAP', msg: '中级·330人在学', img: courseImg3 }
    ],

    this.tabsArr = [
      { name: '首页', img: require('../assets/home.png'), active: require('../assets/home_active.png') },
      { name: '发现', img: require('../assets/find.png'), active: require('../assets/find_active.png') },
      { name: '下载', img: require('../assets/download.png'), active: require('../assets/download_active.png') },
      { name: '我的', img: require('../assets/my.png'), active: require('../assets/my_active.png') }
    ]

  }
}
</script>

<style scoped>
.nav {
  padding: 0;
  background-color: #eee;
  white-space: nowrap;
  overflow-x: auto;
  font-size: 0;
  margin-top: 45px;
}
.nav li {
  width: 80px;
  display: inline-block;
  padding: 15px 0;
  text-align: center;
}
.nav li * {
  display: block;
  font-size: 12px;
  margin: 0 auto;
}
.nav li img {
  width: 35px;
}
.nav li span {
  margin-top: 10px;
}
</style>