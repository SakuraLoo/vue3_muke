<template>
  <div class="c-detail">

    <div class="videobox">
      <router-link to="/"
                   class="videoReturn"><i class="fa fa-chevron-left"></i></router-link>
      <video src="http://vjs.zencdn.net/v/oceans.mp4" controls="controls"></video>
    </div>

    <!-- navbar -->
    <mt-navbar class="page-part"
               v-model="selected">
      <mt-tab-item id="1">章节</mt-tab-item>
      <mt-tab-item id="2">详情</mt-tab-item>
      <mt-tab-item id="3">评论</mt-tab-item>
      <mt-tab-item id="4">问答</mt-tab-item>
      <mt-tab-item id="5">笔记</mt-tab-item>
    </mt-navbar>

    <!-- tabcontainer -->
    <mt-tab-container v-model="selected">
      <mt-tab-container-item id="1">
        <div class="classInfoBox">
          <h3> {{ classInfo.title }} </h3>
          <p :class="showAll ? false : 'twolines'"> {{ classInfo.msg }} </p>
          <li><i @click="showAll = !showAll" :class="showAll==false ? 'fa fa-angle-down' : 'fa fa-angle-up'"></i></li>
        </div>
        <ul class="question">
          <li v-for="(item,index) in arrQuestion" :key="index">
            <h3> {{ arrTitle[index] }} </h3>
            <p v-html="item"></p>
          </li>
        </ul>
      </mt-tab-container-item>
      <mt-tab-container-item id="2">2</mt-tab-container-item>
      <mt-tab-container-item id="3">3</mt-tab-container-item>
      <mt-tab-container-item id="4">4</mt-tab-container-item>
      <mt-tab-container-item id="5">5</mt-tab-container-item>
    </mt-tab-container>

  </div>
</template>

<script>
export default {
  data () {
    return {
      selected: "1",
      classInfo: {
        title: "",
        msg: ""
      },
      showAll: false,
      tabTitles: [],
      arrQuestion: [],
      arrTitle: ["课程须知", "老师告诉你能学到什么"]
    }
  },
  mounted() {
    this.tabTitles = ["章节","详情","评论","问答","记"];
    this.classInfo =  {
      title: "iOS基础教程之——Camera摄像头",
      msg: "从实例出发介绍我们的Camera，可以实现Camera属性监测，照片拍摄，视频录制，图片展示，录制视频。这可以提供一个简单便捷的拍照与选择图库里图片的功能。另一种方式就是完全自定义拍照的界面与选择图库的界面。"
    },
    this.arrQuestion = [
      "本课程适合客户端产品经理，研发人员一i及对iOS新特性感兴趣的人群",`
      (1)数码相机相关的所有API<br/>
      (2)利用Camera实现相机的各种属性检测<br/>
      (3)利用Camera拍照、保存、遍历相册等功能<br/>
      (4)利用Camera拍摄视频、视频剪辑功能`
    ]
  }
}
</script>

<style scoped>
.videobox {
  width: 100%;
  height: 200px;
  position: relative;
}
.videobox video {
  height: 100%;
}
.videoReturn {
  position: absolute;
  left: 10px;
  top: 10px;
  width: 30px;
  height: 30px;
  background-color: #6c6c6c;
  color: #fff;
  z-index: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.mint-navbar {
  border-bottom: 10px #eee solid;
  margin-bottom: 10px;
}
.mint-navbar .mint-tab-item.is-selected {
  color: #000;
  border-color: #d61e04;
}

.classInfoBox {
  border-bottom: 10px #eee solid;
  margin-bottom: 10px;
  padding: 7px 20px;
}
.classInfoBox h3 {
  font-size: 18px;
  margin-bottom: 10px !important;
}
.classInfoBox p {
  color: #666;
}
.twolines {
  overflow : hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
.classInfoBox li {
  text-align: center;
  font-size: 22px;
  color: #666;
}

.question {
  padding: 0 20px 20px 20px !important;
  border-bottom: 10px #eee solid;
  margin-bottom: 10px;
}
.question h3 {
  font-size: 16px;
  margin: 10px !important;
}
.question p {
  color: #666;
  margin-left: 2em !important;
}
</style>