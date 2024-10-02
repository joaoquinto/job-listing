<script setup>
import { computed, ref, watch } from 'vue'

import FilterJobs from '@/components/Filters/FilterJobs.vue'
import CardJob from '@/components/Cards/CardJob.vue'

const filters = ref([])
const jobs = ref([
  {
    id: 1,
    company: 'Photosnap',
    logo: 'PhotoSnapIcon',
    new: true,
    featured: true,
    position: 'Senior Frontend Developer',
    role: 'Frontend',
    level: 'Senior',
    postedAt: '1d ago',
    contract: 'Full Time',
    location: 'USA Only',
    languages: ['HTML', 'CSS', 'JavaScript'],
    tools: []
  },
  {
    id: 2,
    company: 'Manage',
    logo: 'ManageIcon',
    new: true,
    featured: true,
    position: 'Fullstack Developer',
    role: 'Fullstack',
    level: 'Midweight',
    postedAt: '1d ago',
    contract: 'Part Time',
    location: 'Remote',
    languages: ['Python'],
    tools: ['React']
  },
  {
    id: 3,
    company: 'Account',
    logo: 'AccountIcon',
    new: true,
    featured: false,
    position: 'Junior Frontend Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '2d ago',
    contract: 'Part Time',
    location: 'USA Only',
    languages: ['JavaScript'],
    tools: ['React', 'Sass']
  },
  {
    id: 4,
    company: 'MyHome',
    logo: 'MyHomeIcon',
    new: false,
    featured: false,
    position: 'Junior Frontend Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '5d ago',
    contract: 'Contract',
    location: 'USA Only',
    languages: ['CSS', 'JavaScript'],
    tools: []
  },
  {
    id: 5,
    company: 'Loop Studios',
    logo: 'LoopStudiosIcon',
    new: false,
    featured: false,
    position: 'Software Engineer',
    role: 'Fullstack',
    level: 'Midweight',
    postedAt: '1w ago',
    contract: 'Full Time',
    location: 'Worldwide',
    languages: ['JavaScript', 'Ruby'],
    tools: ['Sass']
  },
  // {
  //   id: 6,
  //   company: 'FaceIt',
  //   logo: 'FaceItIcon',
  //   new: false,
  //   featured: false,
  //   position: 'Junior Backend Developer',
  //   role: 'Backend',
  //   level: 'Junior',
  //   postedAt: '2w ago',
  //   contract: 'Full Time',
  //   location: 'UK Only',
  //   languages: ['Ruby'],
  //   tools: ['RoR']
  // },
  {
    id: 7,
    company: 'Shortly',
    logo: 'ShortyIcon',
    new: false,
    featured: false,
    position: 'Junior Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '2w ago',
    contract: 'Full Time',
    location: 'Worldwide',
    languages: ['HTML', 'JavaScript'],
    tools: ['Sass']
  },
  {
    id: 8,
    company: 'Insure',
    logo: 'InsureIcon',
    new: false,
    featured: false,
    position: 'Junior Frontend Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '2w ago',
    contract: 'Full Time',
    location: 'USA Only',
    languages: ['JavaScript'],
    tools: ['Vue', 'Sass']
  },
  // {
  //   id: 9,
  //   company: 'Eyecam Co.',
  //   logo: 'EyeCamIcon',
  //   new: false,
  //   featured: false,
  //   position: 'Full Stack Engineer',
  //   role: 'Fullstack',
  //   level: 'Midweight',
  //   postedAt: '3w ago',
  //   contract: 'Full Time',
  //   location: 'Worldwide',
  //   languages: ['JavaScript', 'Python'],
  //   tools: ['Django']
  // },
  {
    id: 10,
    company: 'The Air Filter Company',
    logo: 'AirFilterIcon',
    new: false,
    featured: false,
    position: 'Front-end Dev',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '1mo ago',
    contract: 'Part Time',
    location: 'Worldwide',
    languages: ['JavaScript'],
    tools: ['React', 'Sass']
  }
])
const jobsClone = ref([
  {
    id: 1,
    company: 'Photosnap',
    logo: 'PhotoSnapIcon',
    new: true,
    featured: true,
    position: 'Senior Frontend Developer',
    role: 'Frontend',
    level: 'Senior',
    postedAt: '1d ago',
    contract: 'Full Time',
    location: 'USA Only',
    languages: ['HTML', 'CSS', 'JavaScript'],
    tools: []
  },
  {
    id: 2,
    company: 'Manage',
    logo: 'ManageIcon',
    new: true,
    featured: true,
    position: 'Fullstack Developer',
    role: 'Fullstack',
    level: 'Midweight',
    postedAt: '1d ago',
    contract: 'Part Time',
    location: 'Remote',
    languages: ['Python'],
    tools: ['React']
  },
  {
    id: 3,
    company: 'Account',
    logo: 'AccountIcon',
    new: true,
    featured: false,
    position: 'Junior Frontend Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '2d ago',
    contract: 'Part Time',
    location: 'USA Only',
    languages: ['JavaScript'],
    tools: ['React', 'Sass']
  },
  {
    id: 4,
    company: 'MyHome',
    logo: 'MyHomeIcon',
    new: false,
    featured: false,
    position: 'Junior Frontend Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '5d ago',
    contract: 'Contract',
    location: 'USA Only',
    languages: ['CSS', 'JavaScript'],
    tools: []
  },
  {
    id: 5,
    company: 'Loop Studios',
    logo: 'LoopStudiosIcon',
    new: false,
    featured: false,
    position: 'Software Engineer',
    role: 'Fullstack',
    level: 'Midweight',
    postedAt: '1w ago',
    contract: 'Full Time',
    location: 'Worldwide',
    languages: ['JavaScript', 'Ruby'],
    tools: ['Sass']
  },
  // {
  //   id: 6,
  //   company: 'FaceIt',
  //   logo: 'FaceItIcon',
  //   new: false,
  //   featured: false,
  //   position: 'Junior Backend Developer',
  //   role: 'Backend',
  //   level: 'Junior',
  //   postedAt: '2w ago',
  //   contract: 'Full Time',
  //   location: 'UK Only',
  //   languages: ['Ruby'],
  //   tools: ['RoR']
  // },
  {
    id: 7,
    company: 'Shortly',
    logo: 'ShortyIcon',
    new: false,
    featured: false,
    position: 'Junior Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '2w ago',
    contract: 'Full Time',
    location: 'Worldwide',
    languages: ['HTML', 'JavaScript'],
    tools: ['Sass']
  },
  {
    id: 8,
    company: 'Insure',
    logo: 'InsureIcon',
    new: false,
    featured: false,
    position: 'Junior Frontend Developer',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '2w ago',
    contract: 'Full Time',
    location: 'USA Only',
    languages: ['JavaScript'],
    tools: ['Vue', 'Sass']
  },
  // {
  //   id: 9,
  //   company: 'Eyecam Co.',
  //   logo: 'EyeCamIcon',
  //   new: false,
  //   featured: false,
  //   position: 'Full Stack Engineer',
  //   role: 'Fullstack',
  //   level: 'Midweight',
  //   postedAt: '3w ago',
  //   contract: 'Full Time',
  //   location: 'Worldwide',
  //   languages: ['JavaScript', 'Python'],
  //   tools: ['Django']
  // },
  {
    id: 10,
    company: 'The Air Filter Company',
    logo: 'AirFilterIcon',
    new: false,
    featured: false,
    position: 'Front-end Dev',
    role: 'Frontend',
    level: 'Junior',
    postedAt: '1mo ago',
    contract: 'Part Time',
    location: 'Worldwide',
    languages: ['JavaScript'],
    tools: ['React', 'Sass']
  }
])
const allowedToViewFilters = computed(() => filters.value.length > 0)
const marginJobs = computed(() => (allowedToViewFilters.value ? '10px' : '80px'))

function filterAlreadyInFilters(value) {
  return filters.value.find((filter) => filter === value)
}

function setFilter(value) {
  if (filterAlreadyInFilters(value)) return
  filters.value.push(value)
}

function filterJobs(FILTERS) {
  if (FILTERS.length === 0) {
    jobs.value = jobsClone.value
    return
  }

  const tags = jobsClone.value.map((job) => {
    return [job.role, job.level, ...job.languages, ...job.tools]
  })

}

watch(
  filters,
  (newValues) => {
    filterJobs(newValues)
  },
  { deep: true }
)
</script>

<template>
  <section class="container">
    <header class="header"></header>
    <FilterJobs v-model:filters="filters" v-show="allowedToViewFilters" />
    <main class="main">
      <CardJob
        v-for="job in jobs"
        :key="job.id"
        :job="job"
        @update:filter="(value) => setFilter(value)"
      />
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

@media (width > 1000px) {
  .header {
    background-image: url('@/assets/images/bg-header-desktop.svg');
    height: 15dvh;
  }
}
</style>
