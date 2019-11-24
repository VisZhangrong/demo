<template>
  <div id="app">
    <el-tabs v-model="activeName">
      <el-tab-pane label="首页" name="first">首页</el-tab-pane>
      <el-tab-pane label="视屏查询" name="second"><list></list></el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import list from './components/list'
export default {
  name: 'app',
  components: {
    list
  },
  data(){
    return {
      activeName:'first'
    }
  }
}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
