<script setup lang="ts">
defineProps({
  label: {
    type: String
  },
  placeholder: {
    type: String
  }
})
</script>
<template>
  <div v-if="label">
    <label>{{ label }}</label>
  </div>
  <input :placeholder="placeholder" />
</template>
<style scoped>
  input {
    padding: 8px;
    border: 1px solid #C2C2C2;
    border-radius: 5px;
    width: 100%;
  }
</style>