<template>
  <div id="app">
    <ul id="menu">
      <li v-for="food in foods" :key="food" @click="addToOrder">{{ food }}</li>
    </ul>
    <FoodOrder :foodItems="kitchenOrder" />
  </div>
</template>

<script>
import FoodOrder from './components/FoodOrder.vue'

export default {
  name: 'App',
  components: {
    FoodOrder
  },
  data() {
    return {
      foods: ["Pizza","Chicken","Carrots","Falafel"],
      kitchenOrder: []
    }
  },
  methods: {
    addToOrder(e) {
      console.log(e.target.innerText);
      this.kitchenOrder.push(e.target.innerText);
    }
  },
}
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
