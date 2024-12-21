<script setup>
// beforeCreate 和 Created 的代码一律放在 setup 中执行
import { onMounted } from "vue";
const getList = () => {
  setTimeout(() => {
    console.log("发送请求，获取数据");
  }, 2000);
};

// 一进入页面的请求
getList();

// 如果有些代码需要在 mounted 生命周期中执行
onMounted(() => {
  console.log("mounted 生命周期函数 - 1");
});

// 写成函数的调用方式，可以调用多次，不冲突，按照顺序依次执行
onMounted(() => {
  console.log("mounted 生命周期函数 - 2");
});
</script>

<template>
  <div></div>
</template>
