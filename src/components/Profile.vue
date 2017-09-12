<template>
  <div class="profile">
    <h2>个人信息</h2>
    <el-form :label-position="'top'" :model="profile">
      <el-form-item label="姓名">
        <el-input v-model="profile.name"></el-input>
      </el-form-item>
      <el-form-item label="年龄">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="电话">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="邮箱">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  props: ['profile']
}
</script>
