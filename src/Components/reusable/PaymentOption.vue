<template>
  <div
    class="payment-option-container option"
    :class="isselected ? 'selected' : 'unselected'"
    @click="emit('select')"
  >
    <img :src="icon" :alt="imgalt" />
    <p>{{ optiontitle }}</p>
  </div>
</template>

<script setup lang="ts">
interface Props {
  optiontitle: string
  icon: string
  imgalt?: string
  isselected: boolean
}

const props = defineProps<Props>()

const { icon, optiontitle, imgalt, isselected } = props

interface Emits {
  (e: 'select'): void
}

const emit = defineEmits<Emits>()
</script>

<style scoped>
.payment-option-container {
  margin-top: 0.75em;
  display: grid;
  gap: 0.5em;
  padding: 1em;
  cursor: pointer;
  /* Ensure each flex-item is same width */
  flex: 1;
}
.unselected {
  border: solid 2px var(--color-light-grey);
}
</style>
