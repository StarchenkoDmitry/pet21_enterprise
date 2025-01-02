<template>
  <h1>Stady vue</h1>

  <p>name: {{ name }}</p>

  <input 
    type="text" 
    placeholder="Name" 
    v-model="name"
  >

  <button
    @click="addUser()"
  >Add user</button>

  <!-- <div>{{ users }}</div> -->

  <div v-for="(elm, index) in users" :key="index">
    <p>{{ elm.name }}</p>
  </div>

</template>
    
<script>
export default {
  data() {
    return {
      users: [],
      name:"Dimka"
    }
  },
  methods: {
    setName(newName){
      this.name = newName;
    },
    addUser(){
      this.users.push({
        name: this.name
      });
    }
  }
}
</script>

<style scoped>
</style>
