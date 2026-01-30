<script setup lang="ts">
import SkillBar from './SkillBar.vue'

interface Skill {
  name: string
  level: number
}

interface Props {
  category: string
  skills: Skill[]
}

defineProps<Props>()
</script>

<template>
  <div>
    <h3 class="text-xl font-semibold mb-4 text-gray-700">{{ category }}</h3>
    <div class="space-y-3">
      <SkillBar
        v-for="(skill, index) in skills"
        :key="index"
        :name="skill.name"
        :level="skill.level"
      />
    </div>
  </div>
</template>
