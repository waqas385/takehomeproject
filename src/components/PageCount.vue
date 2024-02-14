<script setup lang="ts">
import {ref, onMounted, onUnmounted} from 'vue';
const props = defineProps({
  itemsPerPage: {
    type: Number
  }
});
const pageCount = [10, 25, 50, 100];
const selection = props.itemsPerPage;
pageCount.splice(pageCount.findIndex((item) => item === selection), 1);
const showDatail = ref(false);
const ArrowImageBaseURL = '/src/assets/arrow-';
const toggleButtonSrc = ref(ArrowImageBaseURL+'down.svg');

function showMore() {
  showDatail.value = true;
  toggleButtonSrc.value = ArrowImageBaseURL + 'up.svg';
}

function hideMore() {
  showDatail.value = false;
  toggleButtonSrc.value = ArrowImageBaseURL + 'down.svg';
}

onMounted(() => {
  document.querySelector('#pageNumber')?.addEventListener('mouseover', showMore)
  document.querySelector('#pageNumber')?.addEventListener('mouseout', hideMore)
})

onUnmounted(() => {
  document.querySelector('#pageNumber')?.removeEventListener('mouseover', hideMore)
  document.querySelector('#pageNumber')?.addEventListener('mouseout', hideMore)
})
</script>
<template>
  <div id="pageNumber" :class="['px-4 my-4', {'bg-white rounded-md': showDatail}]">
    <div :class="['flex gap-3', {'pb-2 mb-2 border-b-1 border-gray-500': showDatail}]">
      <b>{{ itemsPerPage }}</b>
      <img :src="toggleButtonSrc" width="12" height="12"/>
    </div>
    <TransitionGroup name="list" tag="div">
      <div v-for="page in pageCount" :class="['pb-2',{'is-hidden': !showDatail}]">
        {{ page }}
      </div>
    </TransitionGroup>
  </div>
</template>
<style scoped>

</style>