<!-- <script>
// setup
// 1. 执行 早于beforeCreate
// 2. setup 函数中，由于此时未创建，this指向undefined
// 3. 数据和函数需要在setup最后return
// 4. 语法糖简化
export default {
  setup() {
    // 数据
    const message = "hello vue3";
    // 函数
    const logMessage = () => {
      console.log("setup函数", this);
    };

    return {
      message,
      logMessage,
    };
  },
  beforeCreate() {
    console.log("beforeCreate函数");
  },
};
</script> -->

<script setup>
const message = "hello vue3";
const logMessage = () => {
  console.log("setup函数", this);
};
</script>

<template>
  <div>{{ message }}</div>
  <button @click="logMessage">输出</button>
</template>
