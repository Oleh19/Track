<template>
  <li class="flex-1">
    <a :class="$attrs" class="flex flex-col items-center p-2 text-xs capitalize">
      <slot></slot>
      {{ page }}
    </a>
  </li>
</template>

<script setup></script>

<script>
export default {
  inheritAttrs: false
}
</script>
