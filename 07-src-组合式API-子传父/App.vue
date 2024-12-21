// 子传父 // 1. 在子组件内部，emit触发事件（编译器宏获取数据） // 2.
在父组件，通过 @ 进行监听 // 局部组件，导入就能用
<script setup>
import { ref } from "vue";
import SonCom from "@/components/son-com.vue";

const money = ref(100);
const getMoney = () => {
  money.value += 10;
};
const changeFn = (newMoney) => {
  money.value = newMoney;
};
</script>

<template>
  <div>
    <h3>
      父组件 - {{ money }}
      <button @click="getMoney">挣钱</button>
    </h3>
    <!-- 通过@监听子组件changemoney事件，触发则触发changeFn，并传入参数5 -->
    <SonCom @change-money="changeFn" car="宝马" :money="money"></SonCom>
  </div>
</template>
