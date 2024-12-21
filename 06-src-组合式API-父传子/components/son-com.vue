<script setup>
// 子组件，由于写了 setup，所以无法直接配置 props 选项
// 此处需要借助 编译器宏 函数，接收父组件传递的数据
const props = defineProps({
  car: String,
  money: Number,
});
console.log(props.car);
</script>

<template>
  <!-- 对于 props 传递过来的数据，模板中可以直接使用 -->
  <div class="son">子组件，{{ car }},{{ money }}</div>
</template>

<style scoped>
.son {
  border: 1px solid #000;
  padding: 30px;
}
</style>
