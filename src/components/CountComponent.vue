<template>
    <div>
        <h1>Count: {{count}}</h1>
        <button @click="handleCount">Count</button>
        <h1>Random: {{randomNumber}}</h1>
        <button @click="handleRandom">Random</button>
    </div>
</template>

<script setup>
    import {ref} from "vue";
    const count = ref(0);
    // khi dùng ref để cập nhật lại giá trị phải truy cập vào value 
    // khi sử dụng thì ko cần value 
    const handleCount = ()=>{
        count.value++;  
    }
    const randomNumber = ref(1);
    const handleRandom = ()=>{
        randomNumber.value = Math.ceil(Math.random() * 10);
        
    }
</script>