<script setup>
import AccountIcon from '@/components/Icons/AccountIcon.vue'
import AirFilterIcon from '@/components/Icons/AirFilterIcon.vue'
import FaceItIcon from '@/components/Icons/FaceItIcon.vue'
import InsureIcon from '@/components/Icons/InsureIcon.vue'
import LoopStudiosIcon from '@/components/Icons/LoopStudiosIcon.vue'
import ManageIcon from '@/components/Icons/ManageIcon.vue'
import MyHomeIcon from '@/components/Icons/MyHomeIcon.vue'
import PhotoSnapIcon from '@/components/Icons/PhotoSnapIcon.vue'
import ShortyIcon from '@/components/Icons/ShortyIcon.vue'
import EyeCamIcon from '@/components/Icons/EyeCamIcon.vue'

import { computed } from 'vue'
import BadgeItem from '@/components/Badges/BadgeItem.vue'
import FilterButton from '@/components/Buttons/FilterButton.vue'

defineProps({ job: Object })
defineEmits(['update:filter'])

const handleIcons = computed(() => {
  return {
    AccountIcon,
    AirFilterIcon,
    EyeCamIcon,
    FaceItIcon,
    InsureIcon,
    LoopStudiosIcon,
    ManageIcon,
    MyHomeIcon,
    PhotoSnapIcon,
    ShortyIcon
  }
})
</script>

<template>
  <div class="card" :class="{ new: job.new }">
    <div class="company-logo">
      <component :is="handleIcons[job.logo]" />
    </div>
    <div class="container-infos">
      <div class="job-info">
        <header class="card-header">
          <h3 class="company-name">{{ job.company }}</h3>
          <div class="badges">
            <BadgeItem name="new!" type="new" v-if="job.new" />
            <BadgeItem name="featured" type="featured" v-if="job.featured" />
          </div>
        </header>
        <div class="more-infos">
          <h4 class="job-position">{{ job.position }}</h4>
          <ul class="list-infos">
            <li class="item">{{ job.postedAt }}</li>
            <li class="item">{{ job.contract }}</li>
            <li class="item">{{ job.location }}</li>
          </ul>
        </div>
      </div>
      <hr class="line" />
      <div class="filter-actions">
        <FilterButton :name="job.role" @update:filter="$emit('update:filter', job.role)" />
        <FilterButton :name="job.level" @update:filter="$emit('update:filter', job.level)" />
        <FilterButton
          v-for="(language, index) in job.languages"
          :name="language"
          :key="index"
          @update:filter="$emit('update:filter', language)"
        />
        <FilterButton
          v-for="(tool, index) in job.tools"
          :name="tool"
          :key="index"
          @update:filter="$emit('update:filter', tool)"
        />
      </div>
    </div>
    </div>

</template>

<style scoped lang="scss">
.card {
  display: flex;
  flex-direction: column;
  min-height: 152px;
  padding: 24px;
  border-radius: 6px 8px 8px 6px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  background-color: #fff;
  & + & {
    margin-top: 24px;
  }
  &-header {
    display: flex;
    align-items: baseline;
    gap: 16px;
    margin-bottom: 16px;
  }

  &.new {
    border-left: 6px solid var(--primary);
  }
}

.container-infos{
  display: flex;
  flex-direction: column;
}

.company-logo {
  margin-bottom: 16px;
}

.company-name {
  color: var(--primary);
}

.job-position {
  color: var(--primary-dark);
  font-weight: 700;
  margin-bottom: 16px;
}

.list-infos {
  display: flex;
  list-style: none;
  margin-bottom: 16px;

  .item {
    color: var(--dark-grayish-cyan);
    &:nth-child(2) {
      &::before,
      &::after {
        padding: 0 8px;
        content: '•';
        color: var(--dark-grayish-cyan);
      }
    }
    & + & {
      margin-left: 16px;
    }
  }
}

.badges {
  display: flex;
  //flex-wrap: wrap;
  gap: 8px;
  overflow-x: auto;
}

.filter-actions {
  margin-top: 16px;
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}


@media (width > 1000px){
  .card{
    flex-direction: row;
    align-items: center;
  }

  .company-logo{
    margin-bottom: 0;
    margin-right: 24px;
  }

  .line{
    display: none;
  }

  .container-infos{
    width: 100%;
    justify-content: space-between;
    flex-direction: row;
  }

}
</style>
