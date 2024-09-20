<template>
    <div>
      <h2>Company: {{ info.company }}</h2>
      <h2>Age: {{ info.age }}</h2>
      <button @click="updateInfo">Update Info</button>
    </div>
  </template>
  
  <script setup>
  import { reactive } from 'vue';
  
  const info = reactive({
    company: 'Rikkei Academy',
    age: 5
  });
  
  const updateInfo = () => {
    info.company = 'Rikkei Education';
    info.age = info.age + 1;
  };
  </script>
  
  <style scoped>
  h2 {
    color: #333;
  }
  button {
    margin-top: 10px;
    padding: 10px;
    background-color: #42b983;
    color: white;
    border: none;
    cursor: pointer;
  }
  button:hover {
    background-color: #358a6d;
  }
  </style>
  