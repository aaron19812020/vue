<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
<!-- 获取共享数据 -->
     <h1>这里是App组件</h1>
    <h3> App组件获取共享数据 </h3>
     <!-- <h3>访问根模块counter——$store.state.counter : {{ this.$store.state.counter }} </h3>
    <h3>访问a模块counter——$store.state.a.counter : {{ $store.state.a.counter }} </h3>

    <h3>同步修改根模块counter:<button @click="$store.commit('increase')">同步修改根模块counter</button></h3>
    <h3>同步修改a模块counter:<button @click="$store.commit('a/increase')">同步修改a模块counter</button></h3>

    <h3>异步修改根模块counter:<button @click="$store.dispatch('increaseAction')">异步修改根模块counter</button></h3>
<h3>异步修改a模块counter:<button @click="$store.dispatch('a/increaseAction')">异步修改a模块counter</button></h3>

<h3>访问根模块getters——$store.getters.doubleCounter : {{ $store.getters.doubleCounter }} </h3>
<h3>访问a模块getters——$store.getters['a/doubleCounter'] : {{ $store.getters['a/doubleCounter'] }} </h3> -->

  <h3>使用mapState访问根组件counter : {{counter}}</h3>
    <h3>使用mapState访问a组件counter : {{counterA}}</h3>
    <hr/> 
    <Index></Index>


  </div>
</template>

<script>
import Index  from './components/Index'
import { mapState } from 'vuex'
export default {
  name: 'App',
  components: { Index },
  computed: mapState({
    //访问store根模块
    counter: function(state){
      return state.counter
    },
    //访问a模块
    counterA: function(state){
      return state.a.counter
    }
  })

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
