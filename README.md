# week-range-demo
基于element-plus的周范围日期选择器 week-range



## NPM安装使用：

#### :sparkles:注意:sparkles:

`本插件基于element-plus开发，使用前需要确保已经安装element-plus依赖!`

`element-plus官方提供了日范围选择器和月范围选择器，没有提供周范围的选择器，于是开发了本插件。`

#### :sparkles:Element-plus官方文档:sparkles:：

https://element-plus.gitee.io/zh-CN/component/date-picker.html#%E9%80%89%E6%8B%A9%E4%B8%80%E6%AE%B5%E6%97%B6%E9%97%B4

#### :sparkles:如何使用:sparkles:：

```
npm install date-picker-week-range@对应版本
```

###### :point_left:main.js：

```js
import { createApp } from 'vue'
import ElementPlus from 'element-plus'  //引入插件
import 'element-plus/theme-chalk/index.css' //默认css样式
import zhCn from 'element-plus/es/locale/lang/zh-cn'   //引入中文包，如果你需要的话
import App from './App.vue'

import weekrange from 'date-picker-week-range'

createApp(App).use(ElementPlus).use(weekrange).mount('#app')
```

###### :point_left:App.vue：

`通过< week-range >使用，如果需要获取时间区间端点的Date对象，可使用下面例子中的方式通过getValue来获取。`

`分隔符（separator），两个日历选择器的默认显示文字（startPlaceHolder和endPlaceHolder）可以自定义传入。`

**注意**：必须引入样式：@import 'date-picker-week-range/style.css'

```vue
<template>
  <div>
     <week-range v-model="value" @getValue="getValue"   :separator="separator" :startPlaceHolder="'Choose Start Week'">
    </week-range>
  </div>
</template>
 
<script>
import { ref } from "vue";

export default {
 setup(){
  const value=ref('')
  const separator="To"

  const getValue = (datevalue) => {
    const value=datevalue
    console.log(value.value)//可以打印查看时间区间端点
  }

  return{
    separator,
    value,
    getValue
  }
 }
}
</script>
 
<style >
@import 'date-picker-week-range/style.css'

</style>
```

