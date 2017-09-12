<template>
  <div id="top-bar">
    <h1 class="logo">TAIL RESUME</h1>
    <div class="login">
      <el-button type="primary" size="mini">注册</el-button>
      <el-button size="mini">登录</el-button>
    </div>
  </div>
</template>

<script>
export default {

}
</script>


<style lang="scss">
#top-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 16px;
  background: #fff;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2);
  h1 {
    font-size: 20px;
  }
}
</style>
