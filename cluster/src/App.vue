<template>
  <div class="grid-container">
      
    <div class="float-child">
      <CircularProgress/>
    </div>
    <div class="float-child">
      <CircularProgress/>
    </div>
  </div>
  
</template>

<script>

import CircularProgress from './components/CircularProgress.vue'



export default {
  name: "App",
  components: {
    CircularProgress,
  },
  methods: {
    
  },
  computed: {
 
  }
}
</script>

<style>
.background {
  background-color: black;
}
.grid-container {
    background-color: black;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 5px;
}
</style>
