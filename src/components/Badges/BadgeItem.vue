<script setup>
defineProps({
  name: String,
  type: {
    type: String,
    validator(value) {
      return ['featured', 'new'].includes(value)
    }
  }
})
</script>

<template>
  <div class="badge" :class="[type === 'featured' ? 'featured' : '', type === 'new' ? 'new' : '']">
    <p class="badge-name">
      {{ name }}
    </p>
  </div>
</template>

<style scoped lang="scss">
.badge {
  display: flex;
  align-items: baseline;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 16px;
  width: fit-content;
}

.badge-name {
  margin-bottom: -4px;
  font-weight: 700;
  text-transform: uppercase;
  text-align: center;
  color: #ffffff;
}

.new {
  background-color: var(--primary);
}
.featured {
  background-color: var(--primary-dark);
}
</style>
