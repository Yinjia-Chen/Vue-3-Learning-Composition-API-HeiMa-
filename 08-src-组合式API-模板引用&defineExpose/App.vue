<script setup>
import TestCom from "@/components/test-com.vue";
import { onMounted, ref } from "vue";

// 模板引用（可以获取 dom，也可以获取组件）
// 1. 调用 ref 函数 生成 ref 对象
// 2. 通过 ref 标识，进行绑定
// 3. 通过 ref 对象，value 即可访问到绑定的元素（必须渲染完后才可绑定）

const inp = ref(null);

// 生命周期钩子 onMounted
onMounted(() => {
  // console.log(inp.value);
  // inp.value.focus();
});

const clickFn = () => {
  inp.value.focus();
};

//-------------------------------------------------

const testRef = ref(null);

const getCom = () => {
  console.log(testRef.value.count);
  testRef.value.sayHi();
};
</script>

<template>
  <div>
    <input ref="inp" type="text" />
    <button @click="clickFn">点击让输入框聚焦</button>
  </div>
  <TestCom ref="testRef"></TestCom>
  <button @click="getCom">获取组件</button>
</template>
