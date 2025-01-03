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

</template>
    
<script>
import User from "./components/User.vue";

export default {
  components: { User },
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
    },
    deleteUser(index){
      this.users.splice(index,1);
    }
  }
}
</script>

<style scoped>
</style>
