<script setup lang="tsx">
  import Risks from './components/Risks.vue';
  import Savings from './components/Savings.vue';
  import Investing from './components/Investing.vue'
  import WhatIs from './components/WhatIs.vue'
</script>

<template>
  <WhatIs />

  <Risks />
  
  <Savings />

  <Investing />
</template>

<style>
  img:hover, p:hover, li:hover, ol:hover, input:hover {
    -webkit-filter: drop-shadow(0 0 2em #ffffff);
    -moz-filter: drop-shadow(0 0 2em #ffffff);
    filter: drop-shadow(0 0 2em #ffffff);
  }
</style>
