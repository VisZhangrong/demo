<template>
  <div>
    <el-form ref="form" :model="form" label-width="80px">
      <el-row :gutter="20">
        <el-col :span="12">
          <el-form-item label="房源类型">
            <el-select v-model="form.houseType">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="12">
          <el-form-item label="审核类型">
            <el-select v-model="form.type">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="12">
          <el-form-item label="是否软装">
            <el-select v-model="form.isRuanZhuang">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="12">
          <el-form-item label="在线状态">
            <el-select v-model="form.state">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="12">
          <el-form-item label="提交人">
            <el-input v-model="form.author"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="12">
          <el-form-item label="审核人">
            <el-input v-model="form.reviewer"></el-input>
          </el-form-item>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="12">
          <el-form-item label="提交时间">
            <el-input v-model="form.startTime" placeholder="开始时间"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="12">
          <el-form-item>
            <el-input v-model="form.endTime" placeholder="结束时间"></el-input>
          </el-form-item>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="12">
          <el-form-item label="审核时间">
            <el-input v-model="form.reviewStartTime" placeholder="开始时间"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="12">
          <el-form-item>
            <el-input v-model="form.reviewEndTime" placeholder="结束时间"></el-input>
          </el-form-item>
        </el-col>
      </el-row>
      <el-form-item>
        <el-button type="primary" @click="onSubmit(true)">确认</el-button>
        <el-button @click="onSubmit(false)">取消</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      form: {
        houseType: "",
        type: "",
        isRuanZhuang: "",
        state: "",
        author: "",
        reviewer: "",
        startTime: "",
        endTime: "",
        reviewStartTime: "",
        reviewEndTime: ""
      }
    };
  },
  methods: {
    onSubmit(action) {
      this.$emit("update", {
        action,
        data: this.form
      })
      window.console.log(this.form);
    }
  }
};
</script>
<style scoped>
</style>