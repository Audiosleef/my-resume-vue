<script setup lang="ts">
interface Props {
  institution: string
  degree: string
  duration: string
  location: string
  description?: string[]
  achievements?: string[]
}

defineProps<Props>()
</script>

<template>
  <div class="border-l-4 border-[#42b883] pl-6 pb-6">
    <div class="flex flex-col md:flex-row md:justify-between md:items-start mb-2">
      <div>
        <h3 class="text-xl font-semibold text-gray-800">{{ degree }}</h3>
        <p class="text-lg text-[#42b883] font-medium">{{ institution }}</p>
      </div>
      <div class="text-sm text-gray-500 md:text-right">
        <p>{{ duration }}</p>
        <p>{{ location }}</p>
      </div>
    </div>

    <div v-if="description" class="mb-3">
      <p v-for="(item, i) in description" :key="i" class="text-gray-600 mb-1">
        {{ item }}
      </p>
    </div>

    <div v-if="achievements && achievements.length > 0">
      <h4 class="text-sm font-semibold text-gray-700 mb-2">Key Achievements:</h4>
      <ul class="list-disc list-inside space-y-1 text-gray-600">
        <li v-for="(achievement, i) in achievements" :key="i">
          {{ achievement }}
        </li>
      </ul>
    </div>
  </div>
</template>
