<template>
    <div>
        <p>Name: {{ userName }}</p>
        <button @click="deleteUser(index)">Delete me</button>
    </div>
</template>

<<script setup>
import { computed } from 'vue';

const {user} = defineProps({
    user: {
        type: Object,
        required: true   
    },
    index:{
        type: Number,
        required: true
    },
    deleteUser:{
        type: Function,
        required: true
    }
});
const userName = computed(()=>`@${user.name}`);
</script>

<style>
</style>