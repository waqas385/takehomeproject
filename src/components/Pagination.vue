<script setup lang="ts">
import {ref} from 'vue';
import Select from './Select.vue';


const noOfItemsPerPage = ref([
  {
    text: 10,
    value: 10,
    selected: true
  },
  {
    text: 25,
    value: 25,
    selected: false
  },
  {
    text: 50,
    value: 50,
    selected: false
  },
  {
    text: 100,
    value: 100,
    selected: false
  }
]);

const sortBy = ref([
  {
    text: 'A-Z',
    value: 'asc',
    selected: true
  },
  {
    text: 'Create date',
    value: 'create_date',
    selected: false
  },
  {
    text: 'Last modified',
    value: 'update_date',
    selected: false
  }
]);

const pages = ref([
{
    text: '1 of 10',
    value: 1,
    selected: true
  },
  {
    text: '2 of 10',
    value: 2,
    selected: false
  },
  {
    text: '3 of 10',
    value: 3,
    selected: false
  },
  {
    text: '4 of 10',
    value: 4,
    selected: false
  },
  {
    text: '5 of 10',
    value: 5,
    selected: false
  },
  {
    text: '6 of 10',
    value: 6,
    selected: false
  },
  {
    text: '7 of 10',
    value: 7,
    selected: false
  },
  {
    text: '8 of 10',
    value: 8,
    selected: false
  },
  {
    text: '9 of 10',
    value: 9,
    selected: false
  },
  {
    text: '10 of 10',
    value: 10,
    selected: false
  },
])

function onNoOfItemsPerPageSelection(event) {
  console.log(event);
}

</script>
<template>
  <div class="px-3 flex justify-between pt-3">
    <div>
      <Select :options="pages" label="Page"/>
    </div>
    <div>
      <Select :options="sortBy" label="Sort by" />
    </div>
    <div>
      <Select :options="noOfItemsPerPage" @change=""/>
    </div>
  </div>
</template>