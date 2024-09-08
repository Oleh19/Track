<template>
  <nav class="sticky bottom-0 z-10 bg-white">
    <ul class="flex items-center justify-around border-t">
      <NavItem v-for="page in navItems" :key="page" :href="`#${page}`">
        <component :is="getIconComponent(page)" class="w-6 h-6" />
      </NavItem>
    </ul>
  </nav>
</template>

<script setup>
import NavItem from './NavItem.vue'

import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'

const navItems = ['timeline', 'activities', 'progress']

const icons = {
  timeline: ClockIcon,
  activities: ListBulletIcon,
  progress: ChartBarIcon
}

const getIconComponent = (page) => icons[page]
</script>
