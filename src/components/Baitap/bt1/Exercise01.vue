  <template>
      <div>
        <p>Số lần bấm: {{ count }}</p>
        <button @click="incrementCount">Bấm vào đây</button>
      </div>
    </template>
    
    <script setup>
    import { ref } from 'vue';
    
    // Tạo biến count với giá trị khởi tạo là 0
    const count = ref(0);
    
    // Hàm xử lý sự kiện click, tăng giá trị count
    const incrementCount = () => {
      count.value++;
    };
    </script>
    
    <style scoped>
    button {
      padding: 10px 20px;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    
    button:hover {
      background-color: #0056b3;
    }
    </style>
    