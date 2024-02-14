<script setup lang="ts">

defineProps({
  buttonType: {
    type: String,
    default: 'primary'
  }
})
</script>
<template>
  <button :class="['shrink-0','is-'+buttonType]"><slot/></button>
</template>
<style scoped>
button {
  color: #fff;
  padding: 8px 12px;
  border-radius: 5px;
}
.is-primary {
  background-color: rgb(25, 25, 163);
}
.is-secondary {
  background-color: rgb(19, 82, 19);
}
.is-optional {
  background-color: #fff;
  color: #000;
}
</style>
