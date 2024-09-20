<template>
  <div>
    <h1>Reactive</h1>
    <p>Id: {{userInfo.id}}</p>
    <p>Name: {{userInfo.name}}</p>
    <button @click="handleIncreaseId">Increase Id</button>
  </div>
</template>

<script setup>
    const userInfo = reactive({
            id:1,
            name:"Nguyễn Văn A"
        }
    ) 
    const handleIncreaseId = ()=>{
        userInfo.id++;
    }
</script>

<style>

</style>