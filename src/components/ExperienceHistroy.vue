<template>
  <div class="work-histroy">
    <h2>工作经历</h2>
    <transition-group name="el-fade-in">
      <el-form class="form" :label-position="'top'" v-for="(item,index) in items" :key="index">
        <el-form-item v-for="(key,index) in keys" :label="labels[key] || key" :key="index">
          <el-input v-model="item[key]"></el-input>
        </el-form-item>
        <!-- <el-form-item label="时间">
                        <el-input v-model="workHistroy.time"></el-input>
                      </el-form-item>
                      <el-form-item label="职位">
                        <el-input v-model="workHistroy.position"></el-input>
                      </el-form-item>
                      <el-form-item label="工作职责">
                        <el-input v-model="workHistroy.duty"></el-input>
                      </el-form-item> -->
        <el-button size="mini" icon="delete" :plain="true" @click="removeItem(index)"></el-button>
        <hr>
      </el-form>
    </transition-group>
    <el-button type="primary" @click="addItem()">增加一项</el-button>
  </div>
</template>
   
<script>
export default {
  props: ['items', 'labels'],
  // data() {
  // return {
  // items: 'items'
  // }
  // },
  computed: {
    keys() {
      return Object.keys(this.items[0])
    }
  },
  methods: {
    addItem() {
      const empty = {}
      this.keys.map(key => {
        empty[key] = ''
      })

      this.items.push(empty)
    },
    removeItem(index) {
      if (this.items.length === 1){
        this.toast()
        return
      } 
      this.items.splice(index, 1)
    },
    toast() {
      this.$message({
        showClose: true,
        message: '警告哦，已经是最后一项喽',
        type: 'warning'
      });
    },
  }
}
</script>
