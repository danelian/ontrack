<script setup>
import { CheckCircleIcon } from '@heroicons/vue/24/solid'
import { ClockIcon, ListBulletIcon, ChartBarIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <header class="sticky top-0 z-20 flex items-center justify-between border-b bg-white p-3">
    <a href="#">
      <img src="./assets/logo.png" alt="Logo" class="h-9">
    </a>
    <a href="#" class="text-sm">
      <div v-if="true" class="flex items-center gap-1">
        Day complete!
        <CheckCircleIcon class="h-7 text-green-500" />
      </div>
      <div v-else class="flex items-center gap-1">
        <div>Progress: <span class="font-mono">20%</span></div>
        <div class="h-3 w-3 rounded-full bg-red-500"></div>
      </div>
    </a>
  </header>

  <main class="flex flex-col flex-grow">

  </main>

  <nav class="sticky bottom-0 z-10 bg-white text-xl">
    <ul class="flex items-center justify-around border-t">
      <li class="flex-1">
        <a href="#timeline" class="flex flex-col items-center p-2 text-xs capitalize text-center">
          <ClockIcon class="w-6 h-6" />
          Timeline
        </a>
      </li>
      <li class="flex-1">
        <a href="#activities" class="flex flex-col items-center p-2 text-xs capitalize text-center">
          <ListBulletIcon class="w-6 h-6" />
          Activities
        </a>
      </li>
      <li class="flex-1">
        <a href="#progress" class="flex flex-col items-center p-2 text-xs capitalize text-center">
          <ChartBarIcon class="w-6 h-6" />
          Progress
        </a>
      </li>
    </ul>
  </nav>

</template>
