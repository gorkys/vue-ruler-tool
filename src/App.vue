<template>
  <div id="app">
    <button @click="visible = !visible">显示/隐藏标尺</button>
    <button @click="presetLine = []">清空</button>
    <button @click="presetLine = [{ type: 'h', site: 100 }, { type: 'v', site: 200 }]">修改</button>
    <section style="margin: 50px;padding: 50px;border: 1px solid red;height: 600px;">
      <vue-ruler-tool
        v-model="presetLine"
        :step-length="20"
        :parent="true"
        :is-scale-revise="true"
        :visible.sync="visible"
      >
        <img src="https://cn.vuejs.org/images/logo.png" style="width: 300px;height: 300px;margin: 100px;" alt="">
         <!--<iframe src="https://www.baidu.com" width="500" height="300" />-->
      </vue-ruler-tool>
    </section>
  </div>
</template>

<script>
import VueRulerTool from './components/vue-ruler-tool'
export default {
  name: 'app',
  components:{
    VueRulerTool
  },
  data () {
    return {
      presetLine: [{ type: 'h', site: 200 }, { type: 'v', site: 100 }],
      visible: true
    }
  },
  watch: {
    visible(val) {
      console.log(val)
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
