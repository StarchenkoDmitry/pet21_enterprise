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

  <div v-if="users.length === 0">
    User list is empty
  </div>

  <div v-else-if="users.length === 1">
    User list has one element
  </div>

  <div v-else>
    User list has more than one element
  </div>
  
  <User 
    v-for="(element, index) in users" 
    :user="element"
    :key="index"
    :index="index"
    :deleteUser="deleteUser"
  />

  <div>
    <h2>Make a request</h2>
    <button @click="getData">Make</button>
    <p>Response: {{ responseData }}</p>
  </div>

</template>
    
<script>
import axios from "axios";
import User from "./components/User.vue";

export default {
  components: { User },
  data() {
    return {
      users: [],
      name:"Dimka",

      responseData: "",
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
    },
    deleteUser(index){
      this.users.splice(index,1);
    },
    getData(){
      axios.get("http://127.0.0.1:3000/random",{
        withCredentials: true
      })
      .then((response)=>{
        this.responseData = response.data;
      });
    }
  }
}
</script>

<style scoped>
</style>
