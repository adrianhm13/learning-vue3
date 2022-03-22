// Conditional List Rendering in Vue

<template>
  <div>
    <template v-for="(name, index, key) in names">
      <h2 v-if="name === 'Adrian'" :key="name">{{ name }} {{ key }}</h2>
    </template>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      names: ["Adrian", "Laura", "Shiro"],
    };
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
