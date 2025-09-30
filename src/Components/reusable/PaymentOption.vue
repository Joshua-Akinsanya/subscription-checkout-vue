<template>
  <div class="payment-option-container option">
    <img :src="icon" :alt="imgalt" />
    <p>{{ optiontitle }}</p>
  </div>
</template>

<script setup lang="ts">
interface Props {
  optiontitle: string
  icon: string
  imgalt?: string
}

const props = defineProps<Props>()

const { icon, optiontitle, imgalt } = props
</script>

<style scoped>
.payment-option-container {
  margin-top: 0.75em;
  display: grid;
  gap: 0.5em;
  border: solid 2px var(--color-light-grey);
  padding: 1em;
}
</style>
