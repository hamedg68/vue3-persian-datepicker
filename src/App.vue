<script lang="ts" setup>
  import { reactive } from 'vue';
  import DatePicker from './components/DatePicker.vue';
  const state = reactive({
    myDate: '',
    show: false,
  });

  setTimeout(() => {
    state.myDate = '2022-10-09';
  }, 1000);
</script>

<template>
  <p>{{ state.myDate }}</p>

  <button @click="state.show = true">show</button>
  <DatePicker
    v-model="state.myDate"
    :show="state.show"
    @close="state.show = false"
    alt-name="rest"
    mode="single"
  ></DatePicker>
</template>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
