<template>
  <nav class="sticky bottom-0 z-10 bg-white">
    <ul class="flex items-center justify-around border-t">
      <NavItem
        v-for="page in navItems"
        :key="page"
        :href="`#${page}`"
        :class="{ 'bg-gray-200 pointer-events-none': page === currentPage }"
        @click="currentPage = page"
      >
        <component :is="getIconComponent(page)" class="w-6 h-6" />
        {{ page }}
      </NavItem>
    </ul>
  </nav>
</template>

<script setup>
import NavItem from './NavItem.vue'

import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
import { ref } from 'vue'

const navItems = ['timeline', 'activities', 'progress']

const icons = {
  timeline: ClockIcon,
  activities: ListBulletIcon,
  progress: ChartBarIcon
}

const currentPage = ref('timeline')
const getIconComponent = (page) => icons[page]
</script>
