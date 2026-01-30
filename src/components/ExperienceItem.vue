<script setup lang="ts">
interface Props {
  company: string
  position: string
  duration: string
  location: string
  description: string[]
  technologies: string[]
}

defineProps<Props>()
</script>

<template>
  <div class="border-l-4 border-[#42b883] pl-6 pb-6">
    <div class="flex flex-col md:flex-row md:justify-between md:items-start mb-2">
      <div>
        <h3 class="text-xl font-semibold text-gray-800">{{ position }}</h3>
        <p class="text-lg text-[#42b883] font-medium">{{ company }}</p>
      </div>
      <div class="text-sm text-gray-500 md:text-right">
        <p>{{ duration }}</p>
        <p>{{ location }}</p>
      </div>
    </div>

    <ul class="list-disc list-inside space-y-1 text-gray-600 mb-4">
      <li v-for="(item, i) in description" :key="i">{{ item }}</li>
    </ul>

    <div class="flex flex-wrap gap-2">
      <span
        v-for="(tech, i) in technologies"
        :key="i"
        class="px-3 py-1 bg-[#42b883]/10 text-[#42b883] text-sm rounded-full font-medium"
      >
        {{ tech }}
      </span>
    </div>
  </div>
</template>
