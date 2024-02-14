<template>
    <div>
        {{ myprop }}
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue';
    // const props = defineProps({myprop:String})
    // console.log(props)

    defineProps(["myprop"])
  </script>