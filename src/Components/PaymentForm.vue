<template>
  <div class="payment-container">
    <img src="../assets/images/neuralite-logo.svg" alt="" />
    <div class="mt-16 mb-32">
      <h1 class="heading mb-12">Upgrade to Plus</h1>
      <p class="color-dark-grey small-text">
        Upgrade today and take your AI-powered productivity to the next level.
      </p>
    </div>

    <TextField label="Billed to" placeholder="Enter first & last name" />
    <div class="mb-16">
      <p class="color-dark-grey small-text wt-600">Payment Details</p>

      <div class="options-container-row">
        <PaymentOption
          v-for="option in paymentOptions"
          :key="option.option"
          :optiontitle="option.option"
          :icon="option.icon"
          :imgalt="option.alt"
          :isselected="checkIfSelected(option)"
          @select="handleSelect(option)"
          return-object
        />
      </div>
    </div>

    <TextField label="Email Address" placeholder="Enter email address" />

    <div class="container-flex">
      <TextField label="Country" placeholder="Finland" />
      <TextField label="Postal Code" placeholder="" />
    </div>

    <div class="button-container">
      <button class="button bg-light-grey">Cancel</button>
      <button class="button bg-primary flex-grow">Subscribe</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import TextField from './reusable/TextField.vue'
import PaymentOption from './reusable/PaymentOption.vue'
import { ref } from 'vue'

interface PaymentOption {
  option: string
  icon: string
  alt?: string
}
const paymentOptions: PaymentOption[] = [
  { option: 'Credit Card', icon: '../../assets/images/atm-card.svg', alt: 'Credit card icon' },
  { option: 'Bank Transfer', icon: '', alt: 'Bank icon' },
  { option: 'Points', icon: '', alt: 'Points icon' },
]

const selectedOption = ref<PaymentOption | null>(paymentOptions[0] ?? null)

function checkIfSelected(option: PaymentOption): boolean {
  if (selectedOption.value ?? null === option) {
    return true
  }
  return false
}

function handleSelect(option: PaymentOption): void {
  selectedOption.value = option
}
</script>

<style scoped>
.payment-container {
  display: grid;
  margin: 0 var(--sm-screen-side-margin) 1em;
}
.button-container {
  margin-top: 1em;
  display: flex;
  gap: 1em;
}
.options-container-row {
  display: flex;
  gap: 1em;
  flex-wrap: wrap;
}
.container-flex {
  display: flex;
  gap: 0 1.5em;
  flex-wrap: wrap;
}

@media (min-width: 64rem) {
  .payment-container {
    margin-top: 2em;
    flex: 5 1 0;
  }
}
</style>
