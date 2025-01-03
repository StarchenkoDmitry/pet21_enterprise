<template>
    <div>
        <p>Name: {{ userName }}</p>
        <button @click="deleteUser(index)">Delete me</button>
    </div>
</template>

<<script>
export default {
    props:{
        user:{
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
    },
    computed:{
        userName(){
            return `@${this.user.name}`;
        }
    }
}
</script>

<style>
</style>