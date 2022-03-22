// Methods & Event Handling 2

// Use @ to substitute v-on:
// It's possible to add more than one method to an event listener.
// If only one method it's added without parameter, event it's injected
// With more than one method, or parameter, you have to add manually $event as parameter


<template>
  <div>
    <div>
      <h2>{{ name }}</h2>
      <button @click="changeName($event), increment(1, $event)">
        Change Name
      </button>
    </div>
    <div>
      <h2>{{ count }}</h2>
      <button @click="increment(1, $event)">Increment 1</button>
      <button @click="decrement(1, $event)">Decrement 1</button>
      <button @click="increment(5)">Increment 5</button>
      <button @click="decrement(5)">Decrement 5</button>
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
    changeName(event) {
      this.name = "Batman";
      console.log(event);
    },
    increment(num, event) {
      console.log(event);
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
