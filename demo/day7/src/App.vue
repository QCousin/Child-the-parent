<template>
  <div id="app">
    <div class="header">
      
        <span  v-for="(item,index) in tabList" :key="index">{{item.title}}</span>
   
    </div>

  <div class="cont">
    <HelloWorld v-for="(item,index) in tabList" :key="index" :title="item.title" :cont="item.cont" @clickTabFn="tabFn"/>
  </div>
    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      tabList:[
            {
              title:"周一",
              cont:"今天是周一",
            },
            {
              title:"周二",
              cont:"今天是周二",
            },
            {
              title:"周三",
              cont:"今天是周三",
            }
          ]
    }
   
  },
  methods:{
    tabFn(title){
      console.log(title)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
