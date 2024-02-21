<script setup lang="ts">
import Input from '@/components/form/Input.vue';
import Button from '@/components/form/Button.vue';
import Product from '@/components/view/Product.vue';
import {productsData} from '@/products-data';

</script>
<template>
  <div class="p-3 bg-white rounded-md">
    <div class="flex pb-2 space-x-3">
      <Input placeholder="Find a product"/>
      <Button button-type="primary">Search</Button>
    </div>
    <div class="flex space-x-3">
      <Input placeholder="Product name"/>&nbsp;
      <Button button-type="secondary">Add product</Button>
    </div>
    <div class="md:grid md:grid-cols-2 md:gap-3">
      <template v-for="product in productsData">
        <div class="pt-3">
          <Product :product="product">
            <template #title>
              {{ product.name }}
            </template>
          </Product>
        </div>
      </template>
    </div>
  </div>
</template>