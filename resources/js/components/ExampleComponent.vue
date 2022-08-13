<template>
  <div>
    <p>This is an example Vue 3 component</p>
    <p v-text="name"/>
  </div>
</template>

<script setup>

import {onMounted} from 'vue';

defineProps({
  name: {
    type: String,
    required: true
  }
});

onMounted(() => {
  console.log('Mounted Component')
})
</script>

