<script setup lang="ts">
import { onMounted, ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue';
const formModel = ref({})
onMounted(() => {
  // mock data fetching
  setTimeout(() => {
    formModel.value = {
      addrCode: '360203'
    }
  }, 500)
})
</script>

<template>
  <div id="app">
    <HelloWorld v-model="formModel" />
  </div>
</template>

<style>
body {
  font-size: 16px;
  background-color: #f8f8f8;
  -webkit-font-smoothing: antialiased;
}
</style>
