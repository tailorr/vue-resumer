<template>
  <div id="preview">
    <h1>{{resume.profile.name}} |</h1>{{resume.profile.age}}
  </div>
</template>
<script>
export default{
   props:['resume']
}
</script>

<style lang="scss">
  #preview {
    // background: #666;
    padding: 32px;
  }
</style>
