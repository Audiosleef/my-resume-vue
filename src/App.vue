<script setup lang="ts">
import { ref } from 'vue'
import Navbar from './components/Navbar.vue'
import Banner from './components/Banner.vue'
import About from './components/About.vue'
import Experience from './components/Experience.vue'
import Education from './components/Education.vue'
import Skills from './components/Skills.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

const activeSection = ref('about')

const handleSectionChange = (section: string) => {
  activeSection.value = section
}
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <Navbar @section-change="handleSectionChange" />
    <Banner />

    <div class="max-w-6xl mx-auto px-4 py-16">
      <About v-if="activeSection === 'about'" />
      <Experience v-if="activeSection === 'experience'" />
      <Education v-if="activeSection === 'education'" />
      <Skills v-if="activeSection === 'skills'" />
      <Contact v-if="activeSection === 'contact'" />
    </div>

    <Footer />
  </div>
</template>
