<!-- App.vue -->
<template>
  <div>
    <h1>Shopping Cart</h1>
    <ProductList :products="products" @add-to-cart="addToCart" />
    <Cart :cart="cart" @remove-from-cart="removeFromCart" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ProductList from './components/ProductList.vue';
import Cart from './components/CartAdd.vue';

const products = ref([
  { id: 1, name: 'Product 1', price: 10 },
  { id: 2, name: 'Product 2', price: 20 },
  { id: 3, name: 'Product 3', price: 30 }
]);

const cart = ref([]);

const addToCart = (product) => {
  cart.value.push(product);
};

const removeFromCart = (productId) => {
  const index = cart.value.findIndex(item => item.id === productId);
  if (index !== -1) {
    cart.value.splice(index, 1);
  }
};
</script>
