<script setup>
import {ref} from "vue"
import ChildComp from '@/components/ChildComp.vue'
import FirstChild from '@/components/FirstChild.vue'
const username = ref("");
</script>

<template>
    <FirstChild myprop="Hello, Good Morning" />
    <div>
    <ChildComp
      @changeUsername="
        (payload) => {
          username = payload;
        }
      " />
    <p class="username"> Thank You, {{ username }}</p>
  </div>

</template>
<style>

</style>
