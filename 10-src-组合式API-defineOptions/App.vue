<script setup>
import CenterCom from "@/components/center-com.vue";
import { provide, ref } from "vue";

// 1. 跨层传递普通数据
provide("theme-color", "pink");

// 2. 跨层传递响应式数据
const count = ref(100);
provide("count", count);

let timer = setInterval(() => {
  if (count.value >= 105) {
    clearInterval(timer);
  } else {
    count.value++;
  }
}, 2000);

// 3. 跨层级传递函数 => 传递可以修改数据的方法（不要在接收的组件中修改传入的数据）
provide("changeCount", (newCount) => {
  count.value = newCount;
});
</script>

<template>
  <div>
    <h1>顶层组件 - {{ count }}</h1>
    <CenterCom></CenterCom>
  </div>
</template>
