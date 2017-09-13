<template>
  <div class="profile">
    <h2>{{title}}</h2>
    <el-form :label-position="'top'" :model="items">
      <el-form-item v-for="(value, key, index) in items" :key="index" :label="labels[key]">
        <el-input v-model="items[key]"></el-input>
      </el-form-item>
      <!-- <el-form-item label="出生日期">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="性别">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="所在城市">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="期望城市">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="期望职位">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="职业技能">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="目前状态">
        <el-input v-model="profile.region"></el-input>
      </el-form-item>
      <el-form-item label="工作年限">
        <el-input v-model="profile.region"></el-input>
      </el-form-item> -->
    </el-form>
  </div>
</template>

<script>
export default {
  props: ['items', 'title','labels']
}
</script>
