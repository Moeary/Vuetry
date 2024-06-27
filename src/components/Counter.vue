<template>
  <div>
    <button @click="decrement">-</button>
    {{ count }}
    <button @click="increment">+</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const count = ref(0); // 初始值为 0

const increment = () => {
  count.value++;
};

const decrement = () => {
  count.value--;
};
</script>
