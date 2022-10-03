<template>
  <p>
    <strong>{{ name }}</strong>
    {{ price }}
    <button @click="addToCart">Add to Cart</button>
  </p>
</template>

<script>
export default {
  props: {
    name: String,
    price: Number
  },
  setup(props, {attrs, slots, emit}) {
    const addToCart = () => emit("addToCart", props.name);

    return {
      addToCart
    }
  }
}
</script>

<style scoped>

</style>
