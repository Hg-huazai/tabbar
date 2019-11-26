<template>
  <div id="app">
    <router-view></router-view>
    <main-tab-bar></main-tab-bar>
    
  </div>
</template>

<script>
  import MainTabBar  from './components/MainTabBar'
  // import TabBar from './components/tabbar/TabBar'    //把组件导入 
  // import TabBarItem from './components/tabbar/TabBarItem'
  export default {
  name: 'App',
  components: {
    MainTabBar   //注册
  }
}
</script>

<style>
 
</style>
