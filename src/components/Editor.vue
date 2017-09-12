<template>
  <div id="editor">
    <nav class="tabs">
      <ol>
        <li v-for="(icon, index) in icons" :key="index" :class="{active:currentIndex===index}" @click="currentIndex=index">
          <svg class="icon">
            <use :xlink:href="`#icon-${icons[index]}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="panels">
      <li v-show="currentIndex===0">
        <Profile :profile="profile" />
      </li>
      <li v-show="currentIndex===1">
        <WorkHistroy :workHistroy="workHistroy" />
      </li>
    </ol>
  </div>
</template>
<script>
import Profile from './Profile'
import WorkHistroy from './WorkHistroy'
export default {
  components: {
    Profile, WorkHistroy,
  },
  data() {
    return {
      currentIndex: 0,
      icons: ["gerenxinxi", "aihao", "work-copy"],
      profile: { name: '', age: '' },
      workHistroy: [{ company: '', duty: '' }]
    }
  },

}
</script>

<style lang="scss">
#editor {
  display: flex;
  nav.tabs {
    height: 100%;
    padding-top: 32px;
    background: #2c3e50;
    ol {
      width: 80px;
      height: 100%;
      background: #2c3e50;
      li {
        padding: 16px;
        text-align: center;
        .icon {
          width: 24px;
          height: 24px;
        }
        &.active {
          background: #fff;
          .icon {
            fill: #000;
          }
        }
      }
    }
  }
  .panels {
    flex: 1; // padding: 32px;
    width: 100%;
    li {
      height: 100%;
      padding: 32px;
      overflow: auto;
      .form {
        margin-top: 30px;
        hr {
          border: 0;
          background-color: #eee;
          height: 1px
        }
      }
    }
  }
}
</style>
