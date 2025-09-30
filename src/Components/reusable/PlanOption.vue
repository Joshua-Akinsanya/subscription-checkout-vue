<template>
  <div class="option plan-option" :class="isselected ? 'selected' : ''" @click="emits('selected')">
    <input type="radio" name="" id="" />
    <div class="plan-option-texts">
      <p class="wt-600">{{ text }}</p>
      <p class="wt-500">{{ pricetext }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Props {
  text: string
  pricetext: string
  isselected: boolean
}
const props = defineProps<Props>()

interface Emits {
  (e: 'selected'): void
}
const emits = defineEmits<Emits>()

const { text, pricetext, isselected } = props

// Implemented this way because an extension (not sure which)
// prevented me from writing 'selected': isselected in class
// Still doesn't work tho :(
</script>

<style scoped>
.plan-option {
  display: flex;
  gap: 1.5em;
  padding: 1em 1em;
}
.plan-option-texts {
  display: grid;
  gap: 0.75em;
}
</style>
