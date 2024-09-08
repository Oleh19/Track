<template>
  <a href="#" class="text-sm">
    <div class="flex items-center gap-1">
      <span v-if="dayComplete">Day complete!</span>
      <span v-else>Progress: <span class="font-mono">20%</span></span>

      <CheckCircleIcon v-if="dayComplete" class="h-7 text-green-500" />
      <div v-else class="h-3 w-3 rounded-full bg-red-500"></div>
    </div>
  </a>
</template>

<script setup>
import { CheckCircleIcon } from '@heroicons/vue/24/solid'
import { ref } from 'vue'

const dayComplete = ref(true)
</script>
