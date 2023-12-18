<script setup>
import { computed } from 'vue'
import { isNavItemValid } from '../validators'
import { currentPage, navigate } from '../router'
import BaseIcon from './BaseIcon.vue'

const props = defineProps({
  navItem: {
    required: true,
    type: Object,
    validator: isNavItemValid
  }
})

const classes = computed(() => [
  'flex flex-col items-center p-2 text-xs capitalize text-center',
  { 'bg-gray-200 pointer-events-none': props.navItem.page == currentPage.value }
])
</script>

<template>
  <li class="flex-1">
    <a
      :href="`#${navItem.page}`"
      :class="classes"
      @click="navigate(navItem.page)"
    >
      <BaseIcon :name="navItem.icon" class="w-6 h-6" /> {{ navItem.page }}
    </a>
  </li>
</template>
