<template>
    <div>
      <h1>Giỏ hàng</h1>
      <input v-model.number="inputValue" type="number" placeholder="Nhập giá sản phẩm" />
      <button @click="addToCart">Add to cart</button>
      <h3>Giá trị hiện tại từ input: {{ inputValue }}</h3>
      <h3>Tổng tiền trong giỏ hàng: {{ totalPrice }}</h3>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const totalPrice = ref(0);
  
  const inputValue = ref(0);
  
  const addToCart = () => {
    totalPrice.value += inputValue.value;
    inputValue.value = 0;  
  };
  </script>
  
  <style scoped>
  h1 {
    font-size: 24px;
    color: black;
  }
  input {
    margin-bottom: 10px;
    padding: 5px;
    width: 200px;
  }
  button {
    padding: 5px 10px;
    cursor: pointer;
    background-color: #42b983;
    color: white;
    border: none;
    margin-left: 10px;
  }
  button:hover {
    background-color: #358a6d;
  }
  </style>
  