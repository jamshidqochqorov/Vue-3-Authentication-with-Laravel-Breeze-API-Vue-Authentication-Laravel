<script setup>
import { ref,onMounted} from "vue";
import {useAuthStore} from "../stores/auth.js";

const authStore = useAuthStore();

onMounted(async ()=>{
    //get user
    const user  = await authStore.getUser()
})
</script>
<template>
    <div v-if="authStore.user">
        <h1>{{authStore.user?.name}}</h1>
        <h1>{{authStore.user?.email}}</h1>
    </div>
    <h1 v-else>
        go and Login
    </h1>


</template>
