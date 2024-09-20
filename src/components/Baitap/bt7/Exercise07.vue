<template>
    <div>
      <h1>Theo dõi sự thay đổi</h1>
      <input v-model.number="number" type="number" placeholder="Nhập số" />
      <h3>Giá trị hiện tại: {{ number }}</h3>
      <h3>Bình phương của số: {{ squaredNumber }}</h3>
    </div>
  </template>
  
  <script setup>
  import { ref, computed, watch } from 'vue';
  
  const number = ref(0);
  
  const squaredNumber = computed(() => {
    return number.value * number.value;
  });
  
  watch(number, (newValue, oldValue) => {
    console.log(`Giá trị thay đổi từ ${oldValue} thành ${newValue}`);
  });
  </script>
  
  <style scoped>
  input {
    margin-bottom: 10px;
    padding: 5px;
    width: 200px;
  }
  h3 {
    margin: 5px 0;
  }
  </style>
  