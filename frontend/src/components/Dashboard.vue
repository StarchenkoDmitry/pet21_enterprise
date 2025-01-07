<script setup>
const delay =((Math.random()*3) + 1.5)*1000; 
const rand = await new Promise((ok)=>setTimeout(
    ()=>ok(Math.random()),
    delay,
));
console.log("delay:",delay);
</script>

<template>
    Suspense rand: {{ rand }}
</template>