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
        <ExperienceHistroy :items="workHistroy" :labels="{ company: '公司',time:'时间', position: '职位', duty: '工作职责' }" />
      </li>
      <li v-show="currentIndex===2">
        <ExperienceHistroy :items="studyHistroy" :labels="{school: '学校', time: '时间', major: '学科', degree: '学位' }" />
      </li>
      <li v-show="currentIndex===3">
        <ExperienceHistroy :items="projectHistroy" :labels="{name: '项目名称', content: '项目内容',stack:'技术栈'}" />
      </li>
      <li v-show="currentIndex===4">
        <ExperienceHistroy :items="award" :labels="{prize: '奖项', describe: '描述'}" />
      </li>
      <li v-show="currentIndex===5">
        <ExperienceHistroy :items="contact" :labels="{phone: '手机', email: '邮箱',github:'Github',blog:'Blog'}" />
      </li>
    </ol>
  </div>
</template>
<script>
import Profile from './Profile'
import ExperienceHistroy from './ExperienceHistroy'
export default {
  components: {
    Profile, ExperienceHistroy,
  },
  data() {
    return {
      currentIndex: 0,
      icons: ["gerenxinxi", "work-copy", "aihao", "aihao", "aihao", "aihao"],
      profile: { name: '', age: ''},
      workHistroy: [{ company: '', time: '', position: '', duty: '' }],
      studyHistroy: [{ school: '', time: '', major: '', degree: '' }],
      projectHistroy: [{ name: '', content: '', stack: '' }],
      award: [{ prize: '', describe: '' }],
      contact: [{ phone: '', email: '', github: '', blog: '' }]
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
