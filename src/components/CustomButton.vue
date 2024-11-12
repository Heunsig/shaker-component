<script setup>
defineProps({
  label: {
    type: String,
    default: 'Custom Button'
  }
})
</script>

<template>
  <button type="button" class="custom-button">{{ label }}</button>
</template>

<style scoped>
.custom-button {
  background-color: #000;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 0.25rem;
}
</style>