<script setup lang="ts">
import { ref } from 'vue';
import Input from '@/components/form/Input.vue';
import Button from '@/components/form/Button.vue';
import Indicator from '@/components/structural/Indicator.vue';

defineProps({
  product: {
    type: Object,
    required: true
  }
})

const ArrowImageBaseURL = '/src/assets/arrow-';
const showDetail = ref(false);
const toggleButtonSrc = ref(ArrowImageBaseURL+'down.svg');

function toggleDetails() {
  showDetail.value = !showDetail.value;
  toggleButtonSrc.value = ArrowImageBaseURL + (showDetail.value ? 'up.svg' : 'down.svg');
}
</script>
<template>
  <div>
    <div :class="['flex justify-between items-center pb-3', {'border-b-1': !showDetail}]">
      <div class="flex justify-between items-center gap-2">
        <img :src="product.image" width="24px" height="24px">
        <Indicator :indicator-type="product.status"/>
        <slot name="title" />
      </div>
      <img :src="toggleButtonSrc" width="12" height="12" @click="toggleDetails">
    </div>
    <div :class="['product-detail py-4', {'is-hidden': !showDetail}]">
      <div class="flex justify-between">
        <img src="https://placehold.co/300x200.png" class="shrink">
        <div class="flex flex-col justify-center items-center ">
          <Button button-type="primary">Replace</Button>
          <Button button-type="optional">Clear</Button>
        </div>
      </div>
      <div class="pt-2">
        <Input label="Image title" placeholder="Image title"/>
      </div>
      <div class="pt-2">
        <Input label="Alt text" placeholder="Alt text"/>
      </div>
      <div class="pt-2">
        <Input label="Link" placeholder="Link"/>
      </div>
    </div>
  </div>
</template>
