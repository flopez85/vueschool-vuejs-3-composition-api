<template>
  <h1>{{ name }}</h1>
  <button @click="placeOrder">Place order</button>
</template>

<script>
export default {
  setup() {
    const name = "The Snazzy Burger";
    const placeOrder = () => alert('order placed!')
    return { name, placeOrder }
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
