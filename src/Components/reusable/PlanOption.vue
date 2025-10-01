<template>
  <div
    class="option plan-option"
    :class="isselected ? 'selected' : ''"
    @click="emits('selected')"
    tabindex="0"
  >
    <div class="pos-relative center-block">
      <input type="radio" class="radio-input" name="" :id="plantextNoWhiteSpace" />
      <label :for="plantextNoWhiteSpace" class="radio-label selected"></label>
    </div>
    <div class="plan-option-texts">
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

// This variable will be used for id of each plan input
const plantextNoWhiteSpace = computed(() => {
  return text.replace(/ /g, '')
})
// Implemented this way because an extension (not sure which)
// prevented me from writing 'selected': isselected in class
// Still doesn't work tho :(
</script>

<style scoped>
.plan-option {
  display: flex;
  gap: 1.5em;
  padding: 1em 1em;
  cursor: pointer;
}
.plan-option-texts {
  display: grid;
  gap: 0.75em;
}

/* Hide default input and style custom input using label */
.radio-input {
  opacity: 0;
}

.radio-label {
  --radius: 5px;
  position: absolute;
  top: calc(50% - var(--radius));
  left: calc(50% - var(--radius));
  display: block;
  width: calc(2 * var(--radius));
  height: calc(2 * var(--radius));
  border-radius: calc(Infinity * 1px);
  outline: solid 2px var(--color-dark-grey);
  outline-offset: 0.1em;
}
.radio-label.selected {
  background-color: var(--color-primary);
  outline-color: var(--color-primary);
}
</style>
