// Methods & Event Handling 1

<template>
  <div>
    <div>
      <h2>{{ name }}</h2>
      <button v-on:click="name = 'Lalal'">Change Name</button>
    </div>
    <div>
      <h2>{{ count }}</h2>
      <button v-on:click="increment(1)">Increment 1</button>
      <button v-on:click="decrement(1)">Decrement 1</button>
      <button v-on:click="increment(5)">Increment 5</button>
      <button v-on:click="decrement(5)">Decrement 5</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "Adrian",
      count: 0,
    };
  },
  methods: {
    increment(num) {
      return (this.count += num);
    },
    decrement(num) {
      return (this.count -= num);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
