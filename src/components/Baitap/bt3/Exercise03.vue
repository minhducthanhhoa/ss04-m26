<template>
    <div>
      <h2>Width: {{ width }}</h2>
      <h2>Height: {{ height }}</h2>
      <h2>Area: {{ area }}</h2>
      <button @click="increaseWidth">Increase width</button>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const width = ref(50);
  const height = ref(20);
  
  const area = computed(() => width.value * height.value);
  
  const increaseWidth = () => {
    width.value += 10;
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
  