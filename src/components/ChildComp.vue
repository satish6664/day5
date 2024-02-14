<script setup>
import {ref} from "vue"
import {defineEmits} from 'vue';
const username = ref("");
defineEmits(["changeUsername"])
</script>

<template>
  <div>
    <form action="submit" @submit.prevent="$emit('changeUsername', username)">
      <input type="text" v-model="username" placeholder="Enter your name" />
            <button type="sumbit">Change Username</button>
    </form>
    <p>Value: {{ username }}</p>
  </div>
</template>
