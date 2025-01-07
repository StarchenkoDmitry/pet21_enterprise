<script setup>
import { inject, ref } from 'vue';

const my = inject("myself");

const cred = ref({email:"dimka@gmail.com",password:"1234"});

const signUp = ()=>{
    console.log("signUp");
    my.randName();
}
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
        <div>
            MySelf: {{ my.name }}
        </div>
    </div>
</template>

<style>
</style>