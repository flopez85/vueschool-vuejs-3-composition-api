<template>
  <h1>{{ name }}</h1>
  <button @click="placeOrder">Place order</button>
  <YummyMeal name="Hamburger 🍔" :price="5" @addToCart="addItemToCart" />
</template>

<script>
import YummyMeal from "./components/YummyMeal.vue";

export default {
  components: {YummyMeal},
  setup() {
    const name = "The Snazzy Burger";
    const placeOrder = () => alert('order placed!');
    const addItemToCart = (item) => alert(`One ${item} added to the cart!`)
    return {name, placeOrder, addItemToCart}
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
