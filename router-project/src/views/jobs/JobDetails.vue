<template>
  <div v-if="job">
    <h1>Jobs Detail Page</h1>
    <p>{{ job.title }}</p>
    <p>{{ job.details }}</p>
  </div>
  <div v-else>
    <p>Job it's being fetched</p>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      job: null,
    };
  },
  mounted() {
    fetch(`http://localhost:3000/jobs/${this.id}`)
      .then((res) => res.json())
      .then((data) => (this.job = data))
      .catch((error) => console.log(error.message));
  },
  // data() {
  //   return {
  //     id: this.$route.params.id,
  //   };
  // },
};
</script>

<style scoped></style>
