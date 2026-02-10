<script setup lang="ts">
interface PortfolioProject {
  title: string
  description: string
  technologies: string[]
  liveUrl?: string
  githubUrl?: string
}

const projects: PortfolioProject[] = [
  {
    title: 'Personal Website - React Version',
    description:
      'A responsive portfolio website built with React and Tailwind CSS, showcasing my professional experience, skills, and projects.',
    technologies: ['React', 'TypeScript', 'Tailwind CSS', 'Vercel'],
    liveUrl: 'https://jensvanherp.be',
    githubUrl: 'https://github.com/Audiosleef/my-resume',
  },
  {
    title: 'Personal Website - Vue.js Version',
    description:
      'The same portfolio website recreated in Vue.js to demonstrate framework versatility and modern frontend development skills.',
    technologies: ['Vue.js', 'TypeScript', 'Tailwind CSS', 'Vite', 'Vercel'],
    liveUrl: 'https://vue.jensvanherp.be',
    githubUrl: 'https://github.com/Audiosleef/my-resume-vue',
  },
]
</script>

<template>
  <div class="bg-white rounded-lg shadow-md p-8">
    <h2 class="text-3xl font-bold mb-6 text-gray-800">Portfolio</h2>

    <div class="grid md:grid-cols-2 gap-6">
      <div
        v-for="(project, index) in projects"
        :key="index"
        class="border border-gray-200 rounded-lg p-6 hover:shadow-lg transition-shadow"
      >
        <h3 class="text-xl font-semibold text-gray-800 mb-3">{{ project.title }}</h3>
        <p class="text-gray-600 mb-4">{{ project.description }}</p>

        <div class="flex flex-wrap gap-2 mb-4">
          <span
            v-for="tech in project.technologies"
            :key="tech"
            class="px-3 py-1 bg-[#42b883]/10 text-[#42b883] text-sm rounded-full font-medium"
          >
            {{ tech }}
          </span>
        </div>

        <div class="flex gap-3">
          <a
            v-if="project.liveUrl"
            :href="project.liveUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="flex-1 text-center px-4 py-2 bg-[#42b883] text-white rounded-md hover:bg-[#35495e] transition-colors"
          >
            View Live Site
          </a>

          <a
            v-if="project.githubUrl"
            :href="project.githubUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="flex-1 text-center px-4 py-2 border border-[#42b883] text-[#42b883] rounded-md hover:bg-[#42b883]/10 transition-colors"
          >
            View on GitHub
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
