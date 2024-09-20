<template>
    <div>
      <h1>Giỏ hàng</h1>
      
      <!-- Form nhập thông tin sản phẩm -->
      <div>
        <label for="product">Tên sản phẩm:</label>
        <input v-model="form.product" id="product" placeholder="Nhập tên sản phẩm" />
      </div>
  
      <div>
        <label for="quantity">Số lượng:</label>
        <input v-model.number="form.quantity" id="quantity" type="number" placeholder="Nhập số lượng" />
      </div>
  
      <button @click="addToCart">Thêm vào giỏ hàng</button>
  
      <h2>Danh sách sản phẩm trong giỏ hàng</h2>
      <ul>
        <li v-for="(item, index) in cart" :key="index">
          {{ item.product }} - Số lượng: {{ item.quantity }}
        </li>
      </ul>
  
      <h3>Tổng số lượng sản phẩm: {{ totalQuantity }}</h3>
    </div>
  </template>
  
  <script setup>
  import { reactive, computed, watch } from 'vue';
  
  const form = reactive({
    product: '',
    quantity: 0
  });
  
  const cart = reactive([]);
  
  const addToCart = () => {
    if (form.product && form.quantity > 0) {
      cart.push({ ...form });  
      form.product = '';       
      form.quantity = 0;       
    }
  };
  
  const totalQuantity = computed(() => {
    return cart.reduce((total, item) => total + item.quantity, 0);
  });
  
  watch(form, (newValue, oldValue) => {
    console.log('Form thay đổi:', newValue);
  }, { deep: true });
  </script>
  
  <style scoped>
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
    margin-top: 10px;
  }
  button:hover {
    background-color: #358a6d;
  }
  h3, h2 {
    margin-top: 20px;
  }
  </style>
  