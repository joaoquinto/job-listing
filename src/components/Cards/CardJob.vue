<script setup>
 defineProps({ job: Object })
</script>

<template>
  <div class="card">
    <img :src="job.logo" alt="" />
  </div>
</template>

<style scoped lang="scss">
.card {
  min-height: 152px;
  padding: 24px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  background-color: #fff;
  & + & {
    margin-top: 24px;
  }
}
</style>