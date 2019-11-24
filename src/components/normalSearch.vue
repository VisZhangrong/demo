<template>
  <div id="normal-filter-panel">
    <el-form :inline="true" :model="formInline" size='mini' class="demo-form-inline">
        <el-form-item label="城市">
        <el-select v-model="formInline.city">
          <el-option label="区域一" value="shanghai"></el-option>
          <el-option label="区域二" value="beijing"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="产品类型">
        <el-select v-model="formInline.type">
          <el-option label="区域一" value="shanghai"></el-option>
          <el-option label="区域二" value="beijing"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="房源">
        <el-input v-model="formInline.source" placeholder="请输入"></el-input>
      </el-form-item>
      <el-form-item label="状态">
        <el-select v-model="formInline.state">
          <el-option label="区域一" value="shanghai"></el-option>
          <el-option label="区域二" value="beijing"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">查询</el-button>
      </el-form-item>
       <el-form-item>
        <el-button type="primary" @click="onSubmit">重置</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
    data(){
        return {
            formInline:{
                city:'',
                type:'',
                source:'',
                state:''
            }
        }
    },
    methods:{
        onSubmit(){

        }
    }
}
</script>
<style scoped>
.el-form-item--mini.el-form-item, .el-form-item--small.el-form-item{
    margin-bottom: 0px;
}
</style>