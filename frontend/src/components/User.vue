<template>
    <div>
        <p>Name: {{ user.name }}</p>
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
    }
}
</script>

<style>
</style>