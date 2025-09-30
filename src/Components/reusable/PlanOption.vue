<template>
  <div :class="classList" @click="emits('selected')">
    <input type="radio" name="" id="" />
    <div>
      <p>{{ text }}</p>
      <p>{{ pricetext }}</p>
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
const classList = computed<string[]>(() => {
  const classArray: string[] = ['plan-option']
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
  background-color: white;
  border-radius: 0.5em;
  padding: 1em;
  margin: 1em;
  align-items: center;
  cursor: pointer;
}
</style>
