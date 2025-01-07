<script setup>
import SignUp from '@/components/auth/SignUp.vue';
import Dashboard from '@/components/Dashboard.vue';
import { provide, ref } from 'vue';

const name = ref('dimulka');

function randName(){
    name.value = "rand:" + Math.random();
}

provide("myself",{name,randName});


const ob1 = {name:"car1"};

const ref1 = ref(ob1);

console.log("===",ob1 === ref1.value);
console.log(ob1);
console.log(ref1.value);

</script>

<template>
    <h1>Hi world.</h1>
    <div>APP: {{ name }}</div>
    <button @click="randName()">RandName</button>
    <div>
        <SignUp></SignUp>
    </div>

    <div>
        <h2>Suspense</h2>
        <Suspense>
            <!-- компонент с вложенными асинхронными зависимостями -->
            <Dashboard />

            <!-- загрузка состояния через #fallback слот -->
            <template #fallback>
                Загрузка...
            </template>
        </Suspense>
    </div>
</template>

<style scoped>
</style>
