<template>
    <div>  
        <h1>这里是Index.vue组件</h1>
        <h3>Index组件获取共享数据 </h3>
        <!-- <h3>访问b模块counter——$store.state.b.counter ：{{ $store.state.b.counter }}</h3>

          <h3>同步修改b模块counter:<button @click="$store.commit('b/increase')">同步修改b模块counter</button></h3>

          <h3>异步修改b模块counter:<button @click="$store.dispatch('b/increaseAction')">异步修改b模块counter</button></h3>

          <h3>访问b模块getters——$store.getters[''b/doubleCounter'] : {{ $store.getters['b/doubleCounter'] }} </h3> -->

          <h3>使用mapState访问b模块counter ：{{ counterB }}</h3>
    </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
    name: 'Index',
    computed: mapState({
        counterB: function(state){
            return state.b.counter
        }
    })
}
</script>
