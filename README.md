![标尺辅助线.gif](https://upload-images.jianshu.io/upload_images/12792466-b910b0ac21305c52.gif?imageMogr2/auto-orient/strip)
# vue-ruler-tool
---
>一个基于vue的网页标尺辅助线工具

### 特点
- 没有依赖
- 可拖动的辅助线
- 快捷键支持
> 好吧，其实这个组件没什么太多的特点~

### 安装与基本用法
```
$ npm install --save vue-ruler-tool
```
全局注册
```
import Vue from 'vue'
import VueRulerTool from 'vue-ruler-tool'

Vue.component('vue-ruler-tool', VueRulerTool)
```
你现在就可以使用该组件了
```
<template>
  <div id="app">
    <vue-ruler-tool
      :content-layout="{left:200,top:100}"
      :is-scale-revise="true"
      :v-model="presetLine"
    >
      <div class="test"></div>
    </vue-ruler-tool>
  </div>
</template>

<script>
import VueRulerTool from 'vue-ruler-tool'
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
```
### Props
**parent**

类型:`Boolean`

默认值: `false`

限制组件大小在父级内部
```
<vue-ruler-tool :parent="true" >
```
**position**

类型:`String`

默认值: `relative`

可能值:`['absolute', 'fixed', 'relative', 'static', 'inherit']`

规定标尺工具的定位类型
```
<vue-ruler-tool :position="'fixed'" >
```
**isHotKey**

类型: `Boolean`

默认值: `true`

快捷键键开关，目前仅支持快捷键`R`标尺显示开关
```
<vue-ruler-tool :is-hot-key="true" >
```
**visible**

类型: `Boolean`

默认值: `true`

是否显示，如果设为false则隐藏，可通过.sync接收来自`R`快捷键的修改
```
<v-ruler :visible.sync="visible" >
data() {
  return {
    visible: true
  }
}
```
**isScaleRevise**

类型: `Boolean`

默认值: `false`

刻度修正(根据content进行刻度重置),意思就是从内容的位置开始从0计数
```
<vue-ruler-tool :is-scale-revise="ture" >
```

**value(v-model)**

类型: `Array`

默认值: `[]`

接受格式:` [{ type: 'l', site: 50 }, { type: 'v', site: 180 }]`

预置参考线`l`代表水平线，`v`代表垂直线，`site`为Number类型
```
<vue-ruler-tool :v-model="[{ type: 'l', site: 100 }, { type: 'v', site: 200 }]" >
```
**contentLayout**

类型: `Object`

默认值: `{ top: 0, left: 0 }`

内容部分布局分布，及内容摆放位置
```
<vue-ruler-tool :content-layout="{left:200,top:100}" >
```
**stepLength**

类型: `Number`

默认值: `50`

步长设置(10的倍数)
```
<vue-ruler-tool :step-length="100" >
```
### Methods

**quickGeneration**

参数:`[{ type: 'l', site: 100 }, { type: 'v', site: 200 }]`

快速设置参考线，一般用来通过弹窗让用户输入
```
<vue-ruler-tool ref='rulerTool' >
let params=[
        { type: 'l', site: 100 },
        { type: 'v', site: 200 }
]
this.$refs.rulerTool.quickGeneration(params)
```
### 优化项
- [x] 标尺与窗口间距
## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).
