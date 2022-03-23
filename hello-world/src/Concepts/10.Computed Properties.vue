// Computed Properties 

// Writing computed properties allows us to organize 
//better the code, instead of having the operations directly in the template/data
properties 
// Difference between using method to computed properties. When
component rerenders 
// the method has to do the operation again, the computed
property will fired only if there is a change
<template>
  <div>
    <h2>Full name - {{ firstName }} {{ lastName }}</h2>
    <h2>Computed full name - {{ fullName }}</h2>
    <button @click="changeFullName">Change Full Name</button>

    <button @click="items.push({ id: 4, title: 'Test', price: 300 })">
      Add item
    </button>
    <!-- // Better to use computed data with complex logic operations -->
    <h2>Computer Total Items: {{ total }}</h2>
    <h2>Method Total Items: {{ totalMethod() }}</h2>
    <input type="text" v-model="country" />

    <!-- // Data properties, conditional render list -->
    <template v-for="item in items" :key="item.id">
      <h2 v-if="item.price > 100">{{ item.title }} - {{ item.price }}</h2>
    </template>

    <!-- Computed data, conditional render list -->
    <h2 v-for="item in expensiveItems" :key="item.id">
      {{ item.title }} - {{ item.price }}
    </h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      firstName: "Adrian",
      lastName: "Hervas",
      items: [
        {
          id: 1,
          title: "TV",
          price: 100,
        },
        {
          id: 2,
          title: "Phone",
          price: 200,
        },
        {
          id: 3,
          title: "Laptop",
          price: 300,
        },
      ],
      country: "",
    };
  },
  methods: {
    totalMethod() {
      console.log("Method Total");
      return this.items.reduce(
        (total, currentItem) => (total = total + currentItem.price),
        0
      );
    },
    changeFullName() {
      this.fullName = 'Clark Kent'
    }
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        console.log('Changing full name')
        const names = value.split(' ')
        this.firstName = names[0]
        this.lastName = names[1]
      },
    },
    // }() {
    //   console.log("Computed Total");
    // },
    total() {
      return this.items.reduce(
        (total, currentItem) => (total = total + currentItem.price),
        0
      );
    },
    expensiveItems() {
      return this.items.filter((item) => item.price > 100);
    },
  },
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
