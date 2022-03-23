<template>
  <div>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{volume}}</h3>
    <div>
      <button @click="volume += 2">Increase Volume</button>
      <button @click="volume -= 2">Decrease Volume</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      volume: 0
    };
  },
  methods: {
   
  },
  computed: {
    
  },
  watch: {
    volume(newValue, oldValue) {
      console.log('New Value', newValue)
      console.log('Old Value', oldValue)
      if(newValue > oldValue && newValue === 16){
        alert('AAAAAAAAAAAAAAAAAAI')
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
