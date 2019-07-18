<template>
  <div id="app">
    <section style="margin: 50px;padding: 50px;border: 1px solid red;height: 600px;">
      <vue-ruler-tool
        :parent="true"
        :is-scale-revise="true"
        :preset-line="presetLine"
      >
        <img src="https://cn.vuejs.org/images/logo.png" style="width: 300px;height: 300px;margin: 100px;" alt="">
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
      presetLine: [{ type: 'l', site: 200 }, { type: 'v', site: 100 }]
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
