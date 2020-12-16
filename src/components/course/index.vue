<template>
  <div class="c-course">

  <router-link to="/detail">
    <div class="courseBox" v-for="(course,index) in courses"  :key="index">
      <div class="imgbox"><img :src="course.img"/></div>
      <div class="rightBox">
        <h3> {{ course.title }} </h3>
        <p> {{ course.msg }} </p>
      </div>
    </div>
  </router-link>

  </div>

</template>

<script>

export default {
  data () {
    return {
    }
  },
  props: {
    courses: Array
  }
}
</script>

<style scoped>
.c-course {
  overflow: auto;
  height: calc(100% - 93px);
}
.c-course::after,.courseBox::after {
  content: "";
  display: block;
  clear: both;
}
.courseBox {
  height: 75px;
  margin: 20px 20px 0 20px;
}
.courseBox:last-child {
  margin-bottom: 110px;
}
.imgbox,.rightBox {
  height: 100%;
  float: left;
}
.imgbox {
  width: 100px;
  font-size: 18px;
  border-radius: 3px;
  overflow: hidden;
}
.imgbox img {
  height: 100%;
}
.rightBox {
  width: calc(100% - 130px);
  padding: 0 15px;
  font-size: 14px;
}
.rightBox h3 {
  margin: 0;
  font-weight: normal;
}
.rightBox p {
  margin: 5px 0;
  color: #9b9b9b;
}
</style>