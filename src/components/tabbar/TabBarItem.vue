<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive">            <!--最好用div 把插槽给包住 这样属性在div里就不会被替换了-->
      <slot name="item-icon"></slot>
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div :class="{active: isActive}">
      <slot name="item-text"></slot>
    </div>
    <!--<img src="../../assets/img/tabbar/home.svg">
    <div>首页</div>-->
  </div>
</template>

<script>
export default {
  name: "TabBarItem",
  props: {
    path:String
  },
  data()
  {
    return {
      // isActive:true
    }
  },
  methods: {
    itemClick() {
       console.log(111);
     if(this.$router.currentRoute.path==this.path){
        console.log(22);
        return
     }
      this.$router.replace(this.path)
    }
  },
  computed: {
    isActive() {
		
      return this.$route.path.indexOf(this.path) !== -1 
      
    }
  }
}
</script>
<style>
 .tab-bar-item {
   flex: 1;
   text-align: center;
   height: 49px;
   font-size: 14px;
 }
 .tab-bar-item img {
   width: 24px;
   height: 24px;
   margin-top: 3px;
   vertical-align: middle;     
   margin-bottom: 2px;
 }
 .active {
   color: red;
 }
</style>