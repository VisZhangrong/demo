<template>
  <div>
    <div class="data-filter">
      <div class="title">
        <div class="left">数据筛选</div>
        <div class="right" @click="dialogVisible = true">高级查询</div>
      </div>
      <div class="normal-filter">
        <normal-search></normal-search>
      </div>
    </div>
    <div class="table-panel">
      <el-table :data="tableData" border style="width: 100%">
        <el-table-column prop="date" label="日期"></el-table-column>
        <el-table-column prop="name" label="姓名"></el-table-column>
        <el-table-column prop="province" label="省份"></el-table-column>
        <el-table-column prop="city" label="市区"></el-table-column>
        <el-table-column prop="address" label="地址"></el-table-column>
        <el-table-column prop="zip" label="邮编"></el-table-column>
        <el-table-column label="操作">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
            <el-button type="text" size="small">编辑</el-button>
          </template>
        </el-table-column>
      </el-table>
    </div>
     <el-dialog
        title="高级搜索"
        :visible.sync="dialogVisible"
        width="50%">
        <advanced-search @update='updateData'></advanced-search>
        </el-dialog>
  </div>
</template>
<script>
import normalSearch from "./normalSearch";
import advancedSearch from './advancedSearch'
export default {
  components: {
    normalSearch,
    advancedSearch
  },
  data(){
      return{
          dialogVisible:false,
          tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        }, {
          date: '2016-05-04',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1517 弄',
          zip: 200333
        }, {
          date: '2016-05-01',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1519 弄',
          zip: 200333
        }, {
          date: '2016-05-03',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1516 弄',
          zip: 200333
        }]
      }
  },
  methods:{
      handleClick(data){
          window.console.log(data)
      },
      updateData(data){
          this.dialogVisible = false
          window.console.log(data)
      }
  }
  
};
</script>
<style scoped>
.data-filter {
  border: 1px gray solid;
}
.title {
  height: 30px;
  border-bottom: 1px gray solid;
  padding: 10px 20px 0 20px;
}
.left {
  float: left;
}
.right {
  float: right;
  cursor: pointer;
}
.right:hover {
  color: #409eff;
}
.normal-filter {
  padding: 10px 20px;
}
.table-panel{
    padding:20px 0;
}
</style>