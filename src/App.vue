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
}
</style>
