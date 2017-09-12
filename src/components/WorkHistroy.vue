<template>
  <div class="work-histroy">
    <h2>工作经历</h2>
    <transition-group name="el-fade-in">
      <el-form class="form" :label-position="'top'" v-for="(work,index) in workHistroy" :key="index">
        <el-form-item label="公司">
          <el-input v-model="workHistroy.company"></el-input>
        </el-form-item>
        <el-form-item label="职位">
          <el-input v-model="workHistroy.position"></el-input>
        </el-form-item>
        <el-form-item label="工作职责">
          <el-input v-model="workHistroy.duty"></el-input>
        </el-form-item>
        <el-button size="mini" icon="delete" @click="removeWorkHistroy(index)"></el-button>
        <hr>
      </el-form>
    </transition-group>
    <el-button type="primary" @click="addWorkHistroy()">增加一项</el-button>
  </div>
</template>
   
<script>
export default {
  props: ['workHistroy'],
  methods: {
    addWorkHistroy() {
      this.workHistroy.push({ company: '', position: '', duty: '' })
    },
    removeWorkHistroy(index) {
      this.workHistroy.splice(index, 1)
    }
  }
}
</script>
