<script setup>
import { onActivated, onDeactivated } from 'vue'
import { timelineItems, timelineItemRefs, scrollToCurrentHour } from '../timeline-items'
import { startTimer, stopTimer } from '../time'
import TheTimelineIndicator from '../components/TheTimelineIndicator.vue'
import TimelineItem from '../components/TimelineItem.vue'

onActivated(() => {
  scrollToCurrentHour()
  startTimer()
})

onDeactivated(stopTimer)
</script>

<template>
  <div class="relative mt-7">
    <TheTimelineIndicator />
    <ul>
      <TimelineItem
        v-for="timelineItem in timelineItems"
        :key="timelineItem.hour"
        :timeline-item="timelineItem"
        ref="timelineItemRefs"
      />
    </ul>
  </div>
</template>
