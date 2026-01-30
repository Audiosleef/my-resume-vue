<script setup lang="ts">
import EducationItem from './EducationItem.vue'

interface EducationData {
  institution: string
  degree: string
  duration: string
  location: string
  description?: string[]
  achievements?: string[]
}

interface Certification {
  name: string
  issuer: string
  date: string
}

const educationData: EducationData[] = [
  {
    institution: 'Karel-de-Grote Hogeschool',
    degree: 'Bachelor in Applied Informatics',
    duration: '2015 - 2018',
    location: 'Antwerp, Belgium',
    description: [
      'Blended learning where this degree is obtained after hours in combination with a full-time job.',
    ],
    achievements: [
      'Finished the course together with 5 other classmates out of 97 people who started with us',
      'Learned about all aspects of technolgy',
      'Chose software/web development as speciality in final year',
      'Completed a succesful internship at BNP Paribas',
    ],
  },
  {
    institution: 'Karel-de-Grote Hogeschool',
    degree: 'Bachelor in Marketing',
    duration: '2008 - 2012',
    location: 'Antwerp, Belgium',
    description: [
      'Comprehensive program covering programming fundamentals, database design, and system architecture.',
    ],
    achievements: [
      'Improved communication skills',
      'Excelled in market research, which in hindsight was an indicator that I should have studied IT',
      'Gained business insights',
      'Learned to come up with extra bullet points to fill up my personal website',
    ],
  },
]

const certifications: Certification[] = [
  {
    name: 'Developing Microservices with Containers, Kubernetes and Microsoft Azure',
    issuer: 'U2U',
    date: '2025',
  },
  {
    name: 'Angular - The Complete Guide',
    issuer: 'Udemy',
    date: '2024',
  },
  {
    name: 'Vue JS',
    issuer: 'Udemy',
    date: '2024',
  },
]
</script>

<template>
  <section id="education" class="py-16 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4">
      <div class="bg-white rounded-lg shadow-md p-8">
        <h2 class="text-3xl font-bold mb-6 text-gray-800">Education</h2>

        <div class="space-y-8 mb-10">
          <EducationItem
            v-for="(education, index) in educationData"
            :key="index"
            v-bind="education"
          />
        </div>

        <div class="border-t border-gray-200 pt-8">
          <h3 class="text-2xl font-semibold mb-6 text-gray-800">Certifications</h3>
          <div class="grid md:grid-cols-2 gap-4">
            <div
              v-for="(cert, index) in certifications"
              :key="index"
              class="bg-gray-50 rounded-lg p-4 border border-gray-200"
            >
              <h4 class="font-semibold text-gray-800">{{ cert.name }}</h4>
              <p class="text-[#42b883] text-sm">{{ cert.issuer }}</p>
              <div class="flex justify-between items-center mt-2">
                <span class="text-xs text-gray-500">{{ cert.date }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
