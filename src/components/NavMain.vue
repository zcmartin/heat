<template>
  <div>
    <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <el-menu-item index="1" @click="toggleTab('FunctionalSchematic')">功能示意图</el-menu-item>
      <el-menu-item index="2" @click="toggleTab('Client')">客户管理</el-menu-item>
      <el-menu-item index="3" @click="toggleTab('charge')">收费管理</el-menu-item>
      <el-menu-item index="4" @click="toggleTab('Debt')">清欠管理</el-menu-item>
      <el-menu-item index="5" @click="toggleTab('Change')">变更管理</el-menu-item>
      <el-menu-item index="6" @click="toggleTab('Blacklist')">黑名单</el-menu-item>
      <el-menu-item index="7" @click="toggleTab('Stop')">暂停</el-menu-item>
    </el-menu>
    <div class="main-content" keep-alive="true">
      <charge  :is="currentTab" ></charge>
    </div>
  </div>

</template>
<script>
  import FunctionalSchematic from './FunctionalSchematic .vue'
  import Client from './Client'
  import charge from './charge'
  import Change from './ClientChange.vue'
  import Blacklist from './Blacklist.vue'
  import Debt from './Debt.vue'
  import Stop from './Stop.vue'

  export default {
    data() {
      return {
      	activeIndex: '1',
        currentTab: 'FunctionalSchematic'
      }
    },
    components: {
      FunctionalSchematic,
      Client,
       charge,
       Change,
      Blacklist,
      Debt,
      Stop
    },
    methods: {
      handleSelect(key, keyPath) {
      }
      ,
        toggleTab: function(tab) {
          this.currentTab = tab; // tab 为当前触发标签页的组件名
        }
     }
  }
</script>
<style scope>
	a {
		display: inline-block;
		text-decoration: none;
	}
  .main-content{
    height: 600px;
  }
</style>
