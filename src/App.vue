<template>
  <h1>{{ name }}</h1>
  <input type="text" v-model="name">
  <button @click="placeOrder">Place order</button>
  <button @click="removeWatcher">Remove Watcher</button>
  <YummyMeal
      v-for="meal in meals"
      :name="meal.name"
      :price="meal.price"
      @addToCart="addItemToCart"
  />
</template>

<script>
import YummyMeal from "./components/YummyMeal.vue";
import {reactive, ref, watch} from "vue";

export default {
  components: {YummyMeal},
  setup() {
    const name = ref("The Snazzy Burger");
    const cart = reactive([])
    const meal = reactive({name: "Hamburger 🍔", price: 5});
    const meals = reactive([
      {name: "Hamburger 🍔", price: 5},
      {name: "Cheeseburger 🧀", price: 6},
      {name: "Impossible Burger 🥕", price: 7},
      {name: "Fries 🍟", price: 7},
    ])
    const placeOrder = () => alert('order placed!');
    const addItemToCart = (item) => cart.push(item);

    const removeWatcher = watch([name, () => [...cart]], (newValue, oldValue) => console.log(newValue, oldValue))

    return {name, placeOrder, addItemToCart, meal, meals, removeWatcher}
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
