<template>
  <h1>{{ name }}</h1>
  <input type="text" v-model="name">
  <button @click="placeOrder">Place order</button>
  <YummyMeal :name="meal.name" :price="meal.price" @addToCart="addItemToCart" />
</template>

<script>
import YummyMeal from "./components/YummyMeal.vue";
import {reactive, ref} from "vue";

export default {
  components: {YummyMeal},
  setup() {
    const name = ref("The Snazzy Burger");
    const meal = reactive({ name: "Hamburger 🍔", price: 5});
    const placeOrder = () => alert('order placed!');
    const addItemToCart = (item) => alert(`One ${item} added to the cart!`)
    return {name, placeOrder, addItemToCart, meal}
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
