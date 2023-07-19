如果不用setup语法糖，则定义的变量，函数需要return出去

### 1.绑定动态事件
```jsx
<template>
 <button @[event]="eventHandle">xxxxx</button>
</template>

<script setup lang="ts">
// 动态事件 -- @[event]
const event = "click";
const eventHandle = () => {}
</script>

<style scoped>
</style>

```

### 2.绑定class
如果绑定的是一个数组，bind里面的数组其实也可以写表达
 * `[isTrue ? 'a' : 'b']`

支持一个静态class，一个动态class => 总共两个
```jsx
<template>
 <div :class="['a', 'b']" :class="c">
    v-bind
 </div>
</template>

<style scoped>
    .a{}
    .b{}
    .c{}
</style>
```

### 3.响应式数据
> 只有ref 和 reactive包裹起来的数据才具有响应式
```jsx
<template>
 <div>
    <input v-model="a" type="text" />
    {{a}}
 </div>
</template>

<script setup lang="ts">
import {ref} from 'vue'
const a = ref('小哈')
</script>

<style scoped>
</style>

```

### 4. v-for
其实就是forEach
v-for 里面还可以嵌套 v-for
需要绑定key
```jsx
<template>
 <div :key="index" v-for="(item, index) in arr">
    {{item}} - {{index}}
 </div>
</template>

<script setup lang="ts">
const arr:string[] = ['nba', 'cba', 'aaa']
</script>

<style scoped>
</style>

```
![image-20230719212625029](https://gitee.com/hanosong/picgo_drawingbed/raw/master/image-20230719212625029.png)

### v-once 和 v-memo
> 只会渲染一次
v-once 是基本数据类型
v-memo 是一个数组, 一般用在v-for中 
    => 空数组 == v-once 
    => 

