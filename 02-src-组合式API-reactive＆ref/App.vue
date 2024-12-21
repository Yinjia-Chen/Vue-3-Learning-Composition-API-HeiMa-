<script setup>
// 1. reactive：接收对象类型的数据，返回响应式的对象
// import { reactive } from "vue";
// const obj = reactive({
//   count: 100,
// });
// const setCount = () => {
//   obj.count++;
// };

// 2. ref：接收简单类型 或 复杂类型，返回一个响应式对象
//    本质：在原有传入数据的基础上，外层包了一层对象，包成了复杂数据类型
//    底层：包成复杂数据类型之后，再借助 reactive 实现响应式
//    1. 注意点：script中访问数据，需要通过 .value
//    2.        template中访问数据，不加 .value

// 统一用 ref
import { ref } from "vue";
const count = ref(0);
console.log(count);
console.log(count.value);

const setCount = () => {
  count.value++;
};
</script>

<template>
  <div>
    <div>{{ count }}</div>
    <button @click="setCount">+1</button>
  </div>
</template>
