<template>
  <div id="app" class="pageMax">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
@media screen and (min-width: 0) {
  html,body,.pageMax {
    height: 100%;
    margin: 0;
    overflow: hidden;
  }
}
* {
  font: 14px/1.5 "PingFang SC","微软雅黑","Microsoft YaHei",Helvetica,"Helvetica Neue",Tahoma,Arial,sans-serif;
}
li {
  list-style: none;
}
h3, p {
  margin: 0 !important;
}
a {
  color: #000;
  text-decoration: none;
}
</style>