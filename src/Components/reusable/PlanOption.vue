<template>
  <div :class="classList" @click="emits('selected')">
    <input type="radio" name="" id="" />
    <div>
      <p class="wt-600">{{ text }}</p>
      <p class="wt-500">{{ pricetext }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

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
const classList = computed<string[]>(() => {
  const classArray: string[] = ['option', 'plan-option']
  if (isselected && !classArray.includes('selected')) {
    classArray.push('selected')
  }
  return classArray
})
</script>

<style scoped>
.plan-option {
  display: flex;
  gap: 1em;
  padding: 1em;
  align-items: center;
  cursor: pointer;
}
</style>
