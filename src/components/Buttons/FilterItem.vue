<script setup>
defineProps({ name: String })
defineEmits(['update:remove'])
</script>

<template>
  <div class="filter">
    <p class="filter-name">{{ name }}</p>
    <div class="filter-remove" @click="$emit('update:remove')">
      <img src="@/assets/images/icon-remove.svg" alt="icon remove" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.filter {
  display: flex;
  align-items: center;
  height: 20px;
  gap: 10px;
  width: fit-content;
  padding: 16px 0 16px 8px;
  border-radius: 8px;
  background-color: var(--light-grayish-cyan-filter);

  &-name {
    color: var(--primary);
    font-weight: 700;
    flex: 1;
  }

  &-remove {
    border-top-right-radius: 8px;
    border-bottom-right-radius: 8px;
    display: flex;
    align-items: center;
    padding: 8px;
    background-color: var(--primary);
    cursor: pointer;

    &:hover {
      background-color: var(--primary-dark);
    }
  }
}
</style>
