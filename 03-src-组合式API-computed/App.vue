<script setup>
// const 计算属性 =computed(() => {
//   return 计算返回的结果
// })

import { ref, computed } from "vue";
// 声明数据，list 是对象
const list = ref([1, 2, 3, 4, 5, 6, 7, 8]);

// 基于 list 派生计算属性，从list中过滤去 > 2
const computedList = computed(() => {
  // list.value 才能得到数组
  return list.value.filter((item) => item > 2);
});

// 定义一个修改数组的方法
const addFn = () => {
  list.value.push(666);
};
</script>

<template>
  <div>
    <div>原始数据：{{ list }}</div>
    <div>计算数据：{{ computedList }}</div>
    <button @click="addFn">修改数据</button>
  </div>
</template>
