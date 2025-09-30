<template>
  <div class="container">
    <img src="../assets/images/neuralite-logo.svg" alt="" />
    <h1 class="heading">Upgrade to Plus</h1>
    <p class="color-dark-grey small-text">
      Upgrade today and take your AI-powered productivity to the next level.
    </p>
    <p class="color-dark-grey small-text wt-600">Billed to</p>
    <input type="text" placeholder="Enter first & last name" class="input-field" />
    <p class="color-dark-grey small-text wt-600">Payment Details</p>
    <input type="radio" name="" id="" />
    <input type="radio" name="" id="" />
    <input type="radio" name="" id="" />

    <p class="color-dark-grey small-text wt-600">Email Address</p>
    <input type="email" name="" id="" placeholder="Enter email address" class="input-field" />
    <p class="color-dark-grey small-text wt-600">Country</p>
    <input type="text" placeholder="Select country" class="input-field" />
    <p class="color-dark-grey small-text wt-600">Postal Code</p>
    <input type="text" placeholder="Enter postal code" class="input-field" />
    <div class="button-container">
      <button class="button bg-light-grey">Cancel</button>
      <button class="button bg-primary full-width">Subscribe</button>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.container {
  display: grid;
}
.button-container {
  margin-top: 1em;
  display: flex;
  gap: 1em;
}
.full-width {
  flex-grow: 1;
}
</style>
