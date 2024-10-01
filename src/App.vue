<script setup>
import { computed, ref } from 'vue'

import Jobs from '@/assets/mock/Jobs.json'

import FilterJobs from '@/components/Filters/FilterJobs.vue'
import CardJob from '@/components/Cards/CardJob.vue'

const filters = ref(['HTML5'])
const jobs = ref(Object.assign({}, Jobs))
const allowedToViewFilters = computed(() => filters.value.length > 0)

const marginJobs = computed(() => {
  if (allowedToViewFilters.value) {
    return '10px'
  }else {
    return '80px'
  }
})
</script>

<template>
  <section class="container">
    <header class="header"></header>
    <FilterJobs v-model:filters="filters" v-show="allowedToViewFilters" />
    <main class="main">
        <CardJob v-for="job in jobs" :key="job.id" :job="job" />
    </main>
  </section>
</template>

<style scoped>
.container {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
}

.header {
  background-color: var(--primary);
  background-image: url('@/assets/images/bg-header-mobile.svg');
  height: 20dvh;
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}

.main {
  align-self: center;
  margin: v-bind(marginJobs) 0 90px 0;
  width: 90%;
  height: 100%;
}

@media (width > 501px) {
  .header {
    background-image: url('@/assets/images/bg-header-desktop.svg');
    height: 15dvh;
  }
}
</style>
