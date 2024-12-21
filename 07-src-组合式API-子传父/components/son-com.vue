<script setup>
const props = defineProps({
  car: String,
  money: Number,
});

console.log(props.car);
console.log(props.money);

const emit = defineEmits(["changeMoney"]);
const buy = () => {
  // 需要 emit 触发事件，传入参数5
  emit("changeMoney", 5);
};
</script>

<template>
  <div class="son">
    子组件，{{ car }},{{ money }}
    <!-- 触发emit事件buy，通过changemoney触发父组件监听，并传入参数5 -->
    <button @click="buy">花钱</button>
  </div>
</template>

<style scoped>
.son {
  border: 1px solid #000;
  padding: 30px;
}
</style>
