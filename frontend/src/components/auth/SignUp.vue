<script setup>
    import { onRenderTracked, onUpdated, ref } from 'vue';
    import api from '@/api';

    const cred = ref({email:"dimka@gmail.com",password:"1234"});

    const signUp = ()=>{
        console.log("signUp");
        api.post(`auth/signup`, cred.value)
        .then(res => {
            console.log("res:",res);
        });
    }

    onRenderTracked(()=>{
        console.log("Renderer")
    });

    onUpdated(()=>{
        console.log("Updated");
        fetch("http://127.0.0.1:3000/")
        .then(async (result)=>{
            console.log(result);
            return await result.text()
            ;
        }).then((res)=>{
            console.log("res:",res);
        })
    });
</script>

<template>
    <div>
        <h2>SignUp Form</h2>
        <form v-on:submit.prevent="signUp">
            <label for="email">Email: </label>
            <input type="email" name="email" v-model="cred.email" placeholder="Email" required>
            <br>
            <label for="password">Password: </label>
            <input type="password" name="password" v-model="cred.password" placeholder="Password" required>
            <button type="submit">SignUp</button>
        </form>
    </div>
</template>

<style>
</style>