<script setup lang="ts">
interface Props {
  name: string
  level: number
}

defineProps<Props>()
</script>

<template>
  <div>
    <div class="flex justify-between mb-1">
      <span class="text-sm font-medium text-gray-700">{{ name }}</span>
      <span class="text-sm text-gray-500">{{ level }}%</span>
    </div>
    <div class="w-full bg-gray-200 rounded-full h-2">
      <div
        class="bg-[#42b883] h-2 rounded-full transition-all duration-300"
        :style="{ width: `${level}%` }"
      ></div>
    </div>
  </div>
</template>
