<template>
  <div class="container">
    <h1 class="heading">Starter Plan</h1>

    <div class="plan-option-container">
      <PlanOption
        v-for="plan in plans"
        :key="plan.text"
        :text="plan.text"
        :pricetext="plan.priceText"
        :isselected="selectedPlan === plan"
        return-object
        @selected="handleSelect(plan)"
      />
    </div>

    <div class="total big-text">
      <p>Total</p>
      <p>{{ totalPrice }}</p>
    </div>

    <p class="extra-small-text color-dark-grey">
      This environment is for demonstration purposes only. Please refrain from entering any actual
      sensitive data.
    </p>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import PlanOption from './reusable/PlanOption.vue'

interface Plan {
  text: string
  priceText: string
  pricePerMonth: number
}

const totalPrice = computed(() => {
  const price = selectedPlan.value?.pricePerMonth
  return `$${price} / month`
})

const plans = ref<Plan[]>([
  { text: 'Pay monthly', priceText: '$20/Month/Member', pricePerMonth: 20 },
  { text: 'Pay Annual', priceText: '$16/Month/Member', pricePerMonth: 16 },
])

const selectedPlan = ref<Plan | null>(plans.value[0] ?? null)

function handleSelect(plan: Plan): void {
  selectedPlan.value = plan
}
</script>

<style scoped>
.container {
  background-color: #d2d5da;
  border-radius: 0.5em;
  padding: 1em;
}

.plan-option-container {
  display: grid;
  gap: 1em;
}

.total {
  display: flex;
  justify-content: space-between;
}
</style>
