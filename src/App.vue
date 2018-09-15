<template>
  <div id="app">
    <vue-ruler-tool
      :content-layout="{left:200,top:100}"
      :is-scale-revise="true"
      :preset-line="presetLine"
    >
      <div class="test"></div>
    </vue-ruler-tool>
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
      presetLine: [{ type: 'l', site: 100 }, { type: 'v', site: 200 }]
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
.test{
  width: 500px;
  height: 500px;
  background-color: #99a9bf;
}
</style>
