<template>
  <h1>Hi world.</h1>
  <h2>{{ title }}</h2>

  <button 
    type="button" 
    @dblclick="this,title = 'double click'"
    @click="changeTitle()"
  >Click on me!</button>
  <button
    @click="changeTitle(Math.random())"
  >
    Random Title
  </button>
</template>
    
<script>
export default {
  data: () => {
    return {
      title: "my first app"
    };
  },
  methods:{
    changeTitle(newTitle = "My dafulte title."){
      this.title = newTitle;
    }
  }
}
</script>

<style scoped>
</style>
