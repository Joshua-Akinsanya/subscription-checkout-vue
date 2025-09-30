<template>
  <div class="payment-container">
    <img src="../assets/images/neuralite-logo.svg" alt="" />
    <div>
      <h1 class="heading">Upgrade to Plus</h1>
      <p class="color-dark-grey small-text">
        Upgrade today and take your AI-powered productivity to the next level.
      </p>
    </div>

    <TextField label="Billed to" placeholder="Enter first & last name" />
    <div class="mb-16">
      <p class="color-dark-grey small-text wt-600">Payment Details</p>

      <div class="options-container-grid">
        <PaymentOption
          v-for="option in paymentOptions"
          :key="option.option"
          :optiontitle="option.option"
          :icon="option.icon"
          :imgalt="option.alt"
        />
      </div>
    </div>

    <TextField label="Email Address" placeholder="Enter email address" />

    <p class="color-dark-grey small-text wt-600">Country</p>
    <input type="text" placeholder="Select country" class="input-field" />

    <TextField label="Postal Code" placeholder="" />

    <div class="button-container">
      <button class="button bg-light-grey">Cancel</button>
      <button class="button bg-primary full-width">Subscribe</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import TextField from './reusable/TextField.vue'
import PaymentOption from './reusable/PaymentOption.vue'

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
.full-width {
  flex-grow: 1;
}
.options-container-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1em;
}
</style>
