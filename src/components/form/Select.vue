<script setup lang="ts">
import {defineEmits} from 'vue';

interface SelectOption {
  text: string | number,
  value: string | number,
  selected?: boolean
}

const emit = defineEmits(['change']);

defineProps({
  options: {
    type: Array<SelectOption>
  },
  label: {
    type: String
  }
});

function doSelect(selectedOption: any) {
  emit('change', selectedOption)
}
</script>
<template>
  <div class="flex justify-items-center">
    <div v-if="label" class="shrink-0 pr-2">
      <label>{{ label }}</label>
    </div>
    <select @change="doSelect" class="pl-2 rounded-md">
      <option
        v-for="option in options"
        :value="option.value"
        :selected="option.selected"
      >{{ option.text }}</option>
    </select>
  </div>
</template>
<style scoped>
select {
  height: 24px;
  width: 100%;
  background: transparent;
  font-weight: 700;
  &:hover {
    background-color: #fff;
  }
}
</style>