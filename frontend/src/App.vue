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


  <Eat>
    <!-- <div>Food</div> -->

    <template v-slot>
      <div>def</div>
    </template>

    <template v-slot:car="{carName}">
      <div>
        <h2>My car is {{ carName }}</h2>
      </div>

    </template>

    <template #meat>
      <div>Zeny</div>
    </template>
    <template #wood>
      <div>ANANASs</div>
    </template>
    <!-- <template #[`${temp3}`]>
      <div>Transformer2000</div>
    </template> -->
    <template #[temp3]>
      <div>Transformer2000</div>
    </template>

    <template #main="{var1}">
      Bind var1: {{ var1 }}
    </template>
  </Eat>

</template>
    
<script>
import axios from "axios";
import User from "./components/User.vue";
import Eat from "./components/Eat.vue";

export default {
  components: { User, Eat },
  data() {
    return {
      users: [],
      name:"Dimka",
      temp3: "robot",

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
