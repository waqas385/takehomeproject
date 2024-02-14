<script setup lang="ts">
import {ref} from 'vue';
import PageCount from './PageCount.vue';

const itemsPerPage = ref(10);
</script>
<template>
  <div class="px-3 flex justify-between">
    <div class="py-4">Page <b>1</b> of <b>10</b></div>
    <div class="py-4">Sort by <b>Sort Order</b></div>
    <div>
      <PageCount :items-per-page="itemsPerPage" />
    </div>
  </div>
</template>