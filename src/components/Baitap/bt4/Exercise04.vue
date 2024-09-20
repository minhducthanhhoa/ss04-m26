<template>
    <div>
      <input v-model="inputValue" placeholder="Nhập giá trị" />
      <ul>
        <li v-for="log in changeLogs" :key="log">{{ log }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue';
  
  const inputValue = ref('');
  
  const changeLogs = ref([]);
  
  watch(inputValue, (newValue, oldValue) => {
    console.log(`Giá trị thay đổi từ "${oldValue}" thành "${newValue}"`);
    changeLogs.value.push(`Giá trị thay đổi từ "${oldValue}" thành "${newValue}"`);
  });
  </script>
  
  <style scoped>
  input {
    margin-bottom: 10px;
    padding: 5px;
    width: 200px;
  }
  
  ul {
    background-color: #f0f8ff;
    padding: 10px;
    border: 1px solid #ccc;
    width: 250px;
  }
  
  li {
    list-style: none;
    margin-bottom: 5px;
  }
  </style>
  