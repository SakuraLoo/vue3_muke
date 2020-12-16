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
          <p :class="classEvent.classMsg"> {{ classInfo.msg }} </p>
          <li><i @click="showAll = !showAll" :class="classEvent.faClass"></i></li>
        </div>
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
      showAll: false
    }
  },
  computed: {
    classEvent: function () {
      if (this.showAll == false) {
        return {
          classMsg: 'twolines',
          faClass: 'fa fa-angle-down'
        };
      } else {
        return {
          classMsg: '',
          faClass: 'fa fa-angle-up'
        };
      }
    }
  },
  mounted() {
    this.classInfo =  {
      title: "iOS基础教程之——Camera摄像头",
      msg: "这篇文章主要介绍了vue实现点击展开,点击收起效果，首先我们需要定义data里面的数据，使用computed对data进行处理,需要的朋友可以参考下。安装vue的步骤在这里就不进行赘述了，下面直接进入正题。  使用computed对data进行处理：以上所述是小编给大家介绍的vue实现点击展开点击收起效果，希望对大家有所帮助，如果大家有任何疑问请给我留言，小编会及时回复大家的。在此也非常感谢大家对脚本之家网站的支持！"
    }
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
</style>