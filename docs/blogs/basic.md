# Vue3基础
## 1. Vue基础
## 2. Vue3与Vue2对比
## 3. Vue3基本原理

--- 
vue3代码如下：
```html
<template>
   <div ref="box"></div>
</template>
import {ref,onMounted} from 'vue'
/*
 setup 方法调用是在生命周期beforeCreate与created 之间
*/
<script>
   setup(){
      var box = ref(null)
      // 由于 template 中的 div 属性 ref 引用了一个对象 box，因此 box 将与这个 div 执行绑定。
      // 但由于 setup 执行时期，还未创建实际的 div，所以如果要进行与 box 的交互，必须在生命周期中间执行获取。
      // onMounted() 中的行为会在声明周期 mounted 中执行。
      onMounted(()=>{
         console.log('onMounted',box.value)
      })
      console.log(box.value)
      return {box}

   }

</script>
```
<page-view :url="'../www/map.html'" />

<script setup>
import PageView from '../components/PageView.vue'
</script>