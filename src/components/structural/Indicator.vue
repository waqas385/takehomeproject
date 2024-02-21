<script setup lang="ts">
defineProps({
  indicatorType: {
    type: String,
    default: 'green'
  }
})
</script>
<template>
  <span :class="['indicator','is-'+indicatorType]"></span>
</template>
<style>
.indicator {
  padding: 4px;
  width: 10px;
  height: 10px;
  border-radius: 100%;
}
.is-green {
  background-color: green;
}
.is-red {
  background-color: red;
}
.is-yellow {
  background-color: yellow;
}
</style>