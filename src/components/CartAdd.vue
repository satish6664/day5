<!-- components/Cart.vue -->
<template>
  <div>
    <h2>Cart</h2>
    <ul>
      <li v-for="product in cart" :key="product.id">
        {{ product.name }} - ${{ product.price }}
        <button @click="removeFromCart(product.id)">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script setup props="props">
import { defineProps, defineEmits } from 'vue';

defineProps(['cart']);
const emit = defineEmits(['remove-from-cart']);

const removeFromCart = (productId) => {
  emit('remove-from-cart', productId);
};
</script>