<script setup lang="ts">
import ExperienceItem from './ExperienceItem.vue'

interface Experience {
  company: string
  position: string
  duration: string
  location: string
  description: string[]
  technologies: string[]
}

const experiences: Experience[] = [
  {
    company: 'Sibelga - AllPhi',
    position: 'Full Stack Developer',
    duration: '05/2025 - Present',
    location: 'Brussels',
    description: [
      'Part of the GIS team at Sibelga',
      'Worked on WebGIS interface that is used by Sibelga technicians to locate gas and electrical cables',
      'Developed new microservices for fetching plans from KLIM/KLIP and processing them in the Sibelga ecosystem',
      'Resolved existing and new bugs throughout the entire Sibelga development stack',
      'Expanded unit testing across most microservices and improved coding/development standards',
    ],
    technologies: [
      'React',
      'TypeScript',
      '.NET',
      'C#',
      'Azure Devops',
      'Jira',
      'Oracle DB',
      'Team Foundation Server',
    ],
  },
  {
    company: 'Vlaamse Overheid – Departement Mobiliteit en Openbare Werken - Geo Solutions',
    position: 'Full Stack Developer',
    duration: '11/2024 - 04/2025',
    location: 'Kontich',
    description: [
      'Developed and implemented new application flow design in Angular',
      'Updated existing application to latest Angular version (19)',
      'Worked with PostgreSQL database using PostGIS for geospatial data',
      'Maintained current code architecture and identified improvements',
      'Handled accident data import, localization, aggregation and snapping to road networks',
    ],
    technologies: [
      'Angular',
      'TypeScript',
      'OpenLayers 3',
      'GeoServer',
      'QGIS',
      'PostgreSQL',
      'PostGIS',
    ],
  },
  {
    company: 'Geo Solutions',
    position: 'Full Stack .NET Developer',
    duration: '07/2024 - 04/2025',
    location: 'Kontich',
    description: [
      'Built Kompas 2.0 platform for stakeholders executing work on public domains',
      'Developed solutions for plan requests via KLIP and KLIM-CICC platforms',
      'Implemented microservices architecture on Azure infrastructure',
      'Created technical analysis and integration testing with XUnit/NUnit',
      'Worked on GIPOD integration for site management and monitoring',
    ],
    technologies: [
      'Vue.js',
      'C#',
      '.NET Core',
      'Azure',
      'OpenLayers',
      'TypeScript',
      'Kubernetes',
      'Docker',
    ],
  },
  {
    company: 'Geo Solutions',
    position: 'Full Stack Developer',
    duration: '08/2024 - 04/2025',
    location: 'Belgium',
    description: [
      'Developed ManyMaps web application for comparing mapping technologies',
      'Created comparative analysis between Azure Maps, Google Maps, TomTom Orbis and AnyMaps',
      'Showcased differences, advantages and disadvantages of various mapping solutions',
      'Implemented clean code practices and Agile/SCRUM methodology',
    ],
    technologies: [
      'Vue.js',
      'TypeScript',
      'JavaScript',
      'CSS',
      'Azure Maps',
      'Google Maps API',
      'TomTom',
    ],
  },
  {
    company: 'SD Worx - Protime',
    position: 'Full Stack .NET Developer / React-Angular',
    duration: '09/2021 - 06/2024',
    location: 'Mechelen',
    description: [
      'Built SD Connect application to synchronize data flow between SD Worx and Protime',
      'Implemented DDD principles and TDD methodology with CQRS and Event Sourcing',
      'Developed APIs and applied complex business logic for incoming data processing',
      'Participated in design sessions with team architect for new features',
      'Worked with microservices architecture and deployed to multiple environments',
    ],
    technologies: [
      'C#',
      '.NET Core',
      'ASP.NET',
      'React',
      'Angular',
      'Entity Framework',
      'SQL Server',
      'Azure DevOps',
    ],
  },
  {
    company: 'Unilin - Protime',
    position: 'Full Stack .NET Developer / React-Angular',
    duration: '09/2021 - 06/2024',
    location: 'Mechelen',
    description: [
      'Created planning report system for Unilin sites',
      'Integrated data from multiple sources into readable Excel format',
      'Developed new page in myProtime environment for weekly and summer period reports',
      'Conducted requirement gathering with business teams',
      'Implemented clean code practices and unit testing',
    ],
    technologies: ['C#', '.NET Core', 'ASP.NET', 'React', 'Entity Framework', 'Excel Integration'],
  },
  {
    company: 'Enersense - Protime',
    position: 'Full Stack .NET / React Developer',
    duration: '09/2021 - 06/2024',
    location: 'Mechelen',
    description: [
      'Developed configuration interface for special calculation counters',
      'Built React page for counter overview and value assignment',
      'Integrated configuration storage in Protime environment',
      'Enabled calculations through API calls within the same project',
      'Participated in daily stand-ups and design sessions',
    ],
    technologies: ['C#', '.NET Core', 'ASP.NET', 'React', 'Entity Framework', 'SQL Server'],
  },
  {
    company: 'Protime',
    position: 'Test Automation QA',
    duration: '02/2019 - 09/2021',
    location: 'Mechelen',
    description: [
      'Maintained automated test suite for myProtime web application',
      'Developed test scenarios using Gherkin, SpecFlow and Selenium',
      'Performed manual and automated testing for new features',
      'Monitored deployments to staging and production environments',
      'Participated in QA guild and improved QA setup processes',
    ],
    technologies: [
      'C#',
      '.NET Core',
      'Selenium',
      'SpecFlow',
      'Gherkin',
      'SQL Server',
      'Azure DevOps',
    ],
  },
  {
    company: 'CTG - BNP Paribas Leasing Solutions',
    position: 'Developer / QA',
    duration: '09/2015 - 02/2019',
    location: 'Brussels',
    description: [
      'Converted rental and leasing documents to dynamic PDFs in "Editique" project',
      'Developed documents in Adobe Lifecycle Manager with JavaScript conditions',
      'Collaborated with business teams for requirements gathering',
      'Conducted UAT testing and coordinated with end users',
      'Implemented conditional document sections based on client requirements',
    ],
    technologies: ['Adobe Lifecycle Manager', 'JavaScript', 'C#', 'SVN', 'AS400'],
  },
]
</script>

<template>
  <section id="experience" class="py-16 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4">
      <div class="bg-white rounded-lg shadow-md p-8">
        <h2 class="text-3xl font-bold text-gray-800 mb-6">Experience</h2>

        <div class="space-y-8">
          <ExperienceItem v-for="(exp, index) in experiences" :key="index" v-bind="exp" />
        </div>
      </div>
    </div>
  </section>
</template>
