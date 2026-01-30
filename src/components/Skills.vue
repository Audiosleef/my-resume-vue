<script setup lang="ts">
import SkillCategory from './SkillCategory.vue'

interface Skill {
  name: string
  level: number
}

interface SkillCategoryData {
  category: string
  skills: Skill[]
}

const skillCategories: SkillCategoryData[] = [
  {
    category: 'Frontend',
    skills: [
      { name: 'React', level: 80 },
      { name: 'Angular', level: 80 },
      { name: 'TypeScript', level: 80 },
      { name: 'JavaScript', level: 80 },
      { name: 'HTML/CSS', level: 80 },
      { name: 'Tailwind CSS', level: 80 },
      { name: 'Vue.js', level: 70 },
    ],
  },
  {
    category: 'Backend',
    skills: [
      { name: 'C#', level: 90 },
      { name: '.NET Core', level: 90 },
      { name: 'REST APIs', level: 85 },
      { name: 'EF Core', level: 80 },
      { name: 'Azure', level: 60 },
    ],
  },
  {
    category: 'Tools & Others',
    skills: [
      { name: 'Git', level: 90 },
      { name: 'SQL', level: 80 },
      { name: 'Firebase', level: 75 },
      { name: 'MongoDB', level: 70 },
      { name: 'PostgreSQL', level: 65 },
      { name: 'Docker', level: 65 },
      { name: 'Jira', level: 65 },
    ],
  },
]

const softSkills = [
  'Problem Solving',
  'Team Collaboration',
  'Communication',
  'Time Management',
  'Adaptability',
  'Critical Thinking',
]
</script>

<template>
  <section id="skills" class="py-16 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4">
      <div class="bg-white rounded-lg shadow-md p-8">
        <h2 class="text-3xl font-bold mb-6 text-gray-800">Skills</h2>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <SkillCategory
            v-for="(category, index) in skillCategories"
            :key="index"
            :category="category.category"
            :skills="category.skills"
          />
        </div>

        <div class="mt-8 pt-6 border-t border-gray-200">
          <h3 class="text-xl font-semibold mb-4 text-gray-700">Soft Skills</h3>
          <div class="flex flex-wrap gap-3">
            <span
              v-for="(skill, index) in softSkills"
              :key="index"
              class="px-4 py-2 bg-gray-100 text-gray-700 rounded-lg hover:bg-[#42b883]/10 hover:text-[#42b883] transition-colors"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
