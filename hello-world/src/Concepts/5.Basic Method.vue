// Methods

<template>
  <div>
    <h2>{{ 2 + 3 + 5 }}</h2>
    <h2>{{ 2 + 3 + 15 }}</h2>
    <h2>Add method - {{ add(2, 2, 2) }}</h2>
    <h2>Multiply method - {{ multiply(2) }}</h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      baseMultipler: 5,
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    multiply(num) {
      return num * this.baseMultipler;
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
