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
        <Profile :items="resume.profile" :title="'个人信息'" :labels="{ name: '姓名', age: '年龄',gender:'性别',location:'所在城市',destination:'期望城市',desiredposition:'期望职位',skills:'职业技能',state:'目前状态',worklife:'工作年限'}"/>
      </li>
      <li v-show="currentIndex===1">
        <ExperienceHistroy :items="resume.workHistroy" :title="'工作经历'" :labels="{ company: '公司',time:'时间', position: '职位', duty: '工作职责' }" />
      </li>
      <li v-show="currentIndex===2">
        <ExperienceHistroy :items="resume.studyHistroy" :title="'教育经历'" :labels="{school: '学校', time: '时间', major: '学科', degree: '学位' }" />
      </li>
      <li v-show="currentIndex===3">
        <ExperienceHistroy :items="resume.projectHistroy" :title="'项目经验'" :labels="{name: '项目名称', content: '项目内容',stack:'技术栈'}" />
      </li>
      <li v-show="currentIndex===4">
        <ExperienceHistroy :items="resume.award" :title="'获奖情况'" :labels="{prize: '奖项', describe: '描述'}" />
      </li>
      <li v-show="currentIndex===5">
        <Profile :items="resume.contact" :title="'联系方式'" :labels="{phone: '手机', email: '邮箱', github: 'Github', blog: '个人博客'}" />
      </li>
    </ol>
  </div>
</template>
<script>
import Profile from './Profile'
import ExperienceHistroy from './ExperienceHistroy'

export default {
  props:['resume'],
  components: {
    Profile, ExperienceHistroy
  },
  data() {
    return {
      currentIndex: 0,
      icons: ["gerenxinxi", "work-copy", "education", "disk", "award", "contact",""],
      // profile: { name: '', age: '',gender:'',location:'',destination:'',desiredposition:'',skills:'',state:'',worklife:''},
      // workHistroy: [{ company: '', time: '', position: '', duty: '' }],
      // studyHistroy: [{ school: '', time: '', major: '', degree: '' }],
      // projectHistroy: [{ name: '', content: '', stack: '' }],
      // award: [{ prize: '', describe: '' }],
      // contact: { phone: '', email: '', github: '', blog: '' }
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
