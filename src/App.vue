<template>
  <div id="app">
    <h1>Welcome To Chez NomNom</h1>
    <h2>Please click on a food item to place your order!</h2>
    <h3>Menu</h3>
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
ul{
  list-style-type: none;
  list-style-position: outside;
  margin: 0;
  padding:0;
}
li{
  margin: 0;
  padding: 0;
}
</style>
