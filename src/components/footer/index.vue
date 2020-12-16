<template>
  <div class="c-footer">

    <li :class="{active:index == activeClass}"
      @click="addClassName(index)"
      v-for="(tab,index) in tabs" :key="index"
    >
      <div class="footer_imgbox"><img :src="tab.img" class="first"/><img :src="tab.active" class="last"/></div>
      <p> {{ tab.name }} </p>
    </li>

  </div>

</template>

<script>
import homeActive from "@/assets/home_active.png"
export default {
  data () {
    return {
      activeClass: 0, // 0为默认选择第一个，-1为不选择
    }
  },
  props: {
    tabs: Array
  },
  methods: {
    addClassName: function (index) {
      this.activeClass = index;
    },
  }
}
</script>

<style scoped>
.c-footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 45px;
  background-color: #fff;
  border-top: 1px #ddd solid;
}
.c-footer li {
  width: 25%;
  height: 100%;
  float: left;
  text-align: center;
}
.footer_imgbox {
  display: block;
  height: calc(100% - 20px);
  line-height: calc(100% - 20px);
}
.footer_imgbox img {
  width: 20px;
  margin: 5px auto;
}
.c-footer li p {
  height: 20px;
  line-height: 20px;
  font-size: 12px;
}
.c-footer li.active p {
  color: #D61E04;
}

.last {
  display: none;
}
.active img {
  width: 22px;
}
.active .first {
  display: none;
}
.active .last {
  display: inline-block;
}
</style>