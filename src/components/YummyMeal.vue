<template>
  <p>
    <strong>{{ name }}</strong>
    {{ pricePrettySentence }}
    <button @click="addToCart">Add to Cart</button>
  </p>
</template>

<script>
import {computed} from "vue";

export default {
  props: {
    name: String,
    price: Number
  },
  setup(props, {attrs, slots, emit}) {
    const addToCart = () => emit("addToCart", props.name);
    const pricePretty = computed(() => `$${props.price.toFixed(2)}`);
    const pricePrettySentence = computed(
        () => `The price of this item is ${pricePretty.value}`
    );

    return { addToCart, pricePrettySentence }
  }
}
</script>

<style scoped>

</style>
