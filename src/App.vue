<template>
  <div class="container">
    <SelectPlan />
    <PaymentForm />
  </div>
</template>

<script setup lang="ts">
import PaymentForm from './Components/PaymentForm.vue'
import SelectPlan from './Components/SelectPlan.vue'
</script>
<style scoped>
.container {
  display: grid;
  gap: 4rem;
  margin-bottom: 3rem; /* Gives breathing room for scrolling down */
}
/* 1024px */
@media (min-width: 64rem) {
  .container {
    display: flex;
    flex-direction: row-reverse;
  }
}
</style>
