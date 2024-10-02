<script setup>
defineProps({ name: String })
defineEmits(['update:filter'])
</script>

<template>
  <button class="button" @click="$emit('update:filter')">
    {{ name }}
  </button>
</template>

<style scoped lang="scss">
.button {
  height: fit-content;
  padding: 8px;
  border-radius: 6px;
  border: none;
  cursor: pointer;
  color: var(--primary);
  font-weight: 800;
  background-color: var(--background);

  &:hover {
    background-color: var(--primary);
    color: var(--background);
    transition: all 0.1s ease-in-out;
  }
}
</style>
