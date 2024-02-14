<script setup lang="ts">
import Products from './components/Products.vue';
import Pagination from './components/Pagination.vue';
</script>

<template>
  <div class="p-4 bg-slate-200">
    <h1 class="text-2xl pb-4">Products</h1>
    <Products>
    </Products>
    <Pagination />
  </div>
</template>