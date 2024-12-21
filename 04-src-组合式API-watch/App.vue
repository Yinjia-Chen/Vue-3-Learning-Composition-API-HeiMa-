<script setup>
import { ref, watch } from "vue";
const count = ref(0);
const nickname = ref("张三");

const changeCount = () => {
  count.value++;
};

const changeNickName = () => {
  nickname.value = "李四";
};

// 1. 监视单个数据的变化
//    watch(ref对象，（newValue，oldValue）=> { ... });
// watch(count, (oldValue, newValue) => {
//   console.log(oldValue, newValue);
// });

// 2. 监视多个数据的变化
//  watch([ref对象1，ref对象2]，(newArr,oldArr) => { ... })
// watch([count, nickname], (newArr, oldArr) => {
//   console.log(newArr, oldArr);
// });

// 3. immedate
// watch(
//   count,
//   (oldValue, newValue) => {
//     console.log(oldValue, newValue);
//   },
//   {
//     immediate: true,
//   }
// );

// 4. deep
const userInfo = ref({
  name: "zs",
  age: 18,
});
const setUserInfo = () => {
  userInfo.value.age++;
};

// deep
// watch(
//   userInfo,
//   (oldValue, newValue) => {
//     console.log(oldValue, newValue);
//   },
//   {
//     deep: true,
//   }
// );

// 5. 对对象中的属性精确侦听
watch(
  // 要侦听的属性
  () => userInfo.value.age,
  (newValue, oldValue) => {
    console.log(newValue, oldValue);
  }
);
</script>

<template>
  <div>{{ count }}</div>
  <button @click="changeCount">改数字</button>
  <div>{{ nickname }}</div>
  <button @click="changeNickName">改昵称</button>
  <div>==================================</div>
  <div>{{ userInfo }}</div>
  <button @click="setUserInfo">修改userInfo</button>
</template>
