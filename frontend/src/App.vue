<template>
  <h1>Stady vue</h1>

  <input 
    type="text" 
    placeholder="Name" 
    @input="setName($event.target.value)"
  >
  <p>name: {{ name }}</p>
  
</template>
    
<script>
export default {
  data() {
    return {
      name:"init name"
    }
  },
  methods: {
    setName(newName){
      this.name = newName;
    }
  }
}
</script>

<style scoped>
</style>
