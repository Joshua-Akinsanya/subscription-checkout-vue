<template>
  <div class="display-grid mb-16 flex-grow">
    <label class="color-dark-grey small-text wt-600" for="">{{ label }}</label>
    <input type="text" :placeholder="placeholder" class="input-field mt-12" />
  </div>
</template>

<script setup lang="ts">
interface Props {
  label: string
  placeholder: string
}

const props = defineProps<Props>()

const { label, placeholder } = props
</script>

<style scoped></style>
