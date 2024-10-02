<script setup>
import FilterItem from '@/components/Buttons/FilterItem.vue'

const filters = defineModel('filters', { type: Array, default: () => [] })

const clearFilters = () => (filters.value = [])

function removeFilterItem(index) {
  filters.value.splice(index, 1)
}
</script>

<template>
  <div class="container-filters">
    <div class="filters">
      <FilterItem
        v-for="(name, index) in filters"
        :key="index"
        :name
        @update:remove="removeFilterItem(index)"
      />
    </div>
    <button class="clear-filters" @click="clearFilters">Clear</button>
  </div>
</template>

<style scoped lang="scss">
.container-filters {
  top: -40px;
  position: relative;
  height: 80px;
  width: 90%;
  padding: 16px 24px;
  display: flex;
  align-items: center;
  margin: 0 auto;
  gap: 20px;
  border-radius: 8px;
  background-color: #ffff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.filters {
  flex: 1;
  display: flex;
  gap: 16px;
  overflow-x: scroll;
}

.clear-filters {
  background-color: transparent;
  border: none;
  cursor: pointer;
  font-weight: 700;
  color: var(--primary);
  font-family: 'League Spartan', sans-serif;
  font-size: 1rem;

  &:hover {
    text-decoration: underline;
  }
}
</style>
