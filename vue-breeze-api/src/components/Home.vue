<script setup>
import { ref,onMounted} from "vue";
import axios from "axios";
const  user = ref();
onMounted(async ()=>{
    const data  = await axios.get('/api/user');
    user.value = data.data

})
</script>
<template>
    <h1>{{user?.name}}</h1>
    <h1>{{user?.email}}</h1>
</template>
