<script setup>
  import { ref, watch } from 'vue';
  const balance = ref(100);
  const rate = ref(12);
  const months = ref(1);
  const interest = ref(0);
  watch([balance, rate, months], 
    ([balance, rate, months], [b, r, m]) => {
    interest.value = balance * (rate / 100 / 12) * months;
  });
</script>

<template>
  <div>
    <label>Balance: </label>
    <input v-model="balance" type="number">
  </div>
  <div>
    <label>Rate: </label>
    <input v-model="rate" type="number">
  </div>
  <div>
    <label>Months: </label>
    <input v-model="months" type="number">
  </div>
  <div>
    <label>Interest: </label>
    <label>{{ interest }}</label>
  </div>
</template>

<style scoped>
</style>
