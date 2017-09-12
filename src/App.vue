<template>
  <div id="app">
    <Topbar class="top-bar" />
    <main>
      <Editor class="editor" />
      <Preview class="preview" />
    </main>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Editor from './components/Editor'
import Preview from './components/Preview'

export default {
  name: 'app',
  components: {
    Topbar, Editor, Preview
  }
}
</script>

<style lang="scss">
html,
body {
  height: 100%;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
  box-sizing: border-box;
}

.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: #fff;
  overflow: hidden;
}

main {
  display: flex;
  height: calc(100% - 39px);
  .editor {
    height: 100%;
    width: 400px;
  }
  .preview {
    flex: 1;
  }
}
</style>
