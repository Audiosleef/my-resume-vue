<script setup lang="ts">
import { ref } from 'vue'

const activeSection = ref('about')
const isMobileMenuOpen = ref(false)

const navItems = [
  { key: 'about', label: 'About' },
  { key: 'experience', label: 'Experience' },
  { key: 'education', label: 'Education' },
  { key: 'skills', label: 'Skills' },
  { key: 'contact', label: 'Contact' },
]

// Emit the active section to parent
const emit = defineEmits<{
  sectionChange: [section: string]
}>()

const handleSectionChange = (section: string) => {
  activeSection.value = section
  isMobileMenuOpen.value = false
  emit('sectionChange', section)
}
</script>

<template>
  <nav class="bg-white shadow-lg sticky top-0 z-50">
    <div class="max-w-6xl mx-auto px-4">
      <div class="flex justify-between items-center py-4">
        <div class="text-xl font-bold text-gray-800">Jens Van Herp</div>

        <!-- Desktop menu -->
        <div class="hidden md:flex space-x-6 items-center">
          <button
            v-for="item in navItems"
            :key="item.key"
            :class="`${
              activeSection === item.key
                ? 'text-[#42b883] font-semibold'
                : 'text-gray-600 hover:text-gray-900'
            }`"
            @click="handleSectionChange(item.key)"
          >
            {{ item.label }}
          </button>

          <!-- Link to React version -->

          <a
            href="https://jensvanherp.be"
            class="px-3 py-1 bg-blue-500 text-white rounded-md hover:bg-blue-600 transition-colors text-sm"
          >
            React Version
          </a>
        </div>

        <!-- Mobile hamburger button -->
        <div class="md:hidden">
          <button
            @click="isMobileMenuOpen = !isMobileMenuOpen"
            class="text-gray-600 hover:text-gray-900 focus:outline-none"
          >
            <div class="w-6 h-6 flex flex-col justify-center items-center">
              <div
                :class="`w-5 h-0.5 bg-current transform transition duration-300 ${
                  isMobileMenuOpen ? 'rotate-45 translate-y-1.5' : ''
                }`"
              ></div>
              <div
                :class="`w-5 h-0.5 bg-current transition duration-300 ${
                  isMobileMenuOpen ? 'opacity-0' : 'mt-1'
                }`"
              ></div>
              <div
                :class="`w-5 h-0.5 bg-current transform transition duration-300 ${
                  isMobileMenuOpen ? '-rotate-45 -translate-y-1.5' : 'mt-1'
                }`"
              ></div>
            </div>
          </button>
        </div>
      </div>

      <!-- Mobile menu -->
      <div v-if="isMobileMenuOpen" class="md:hidden pb-4 border-t border-gray-200">
        <div class="pt-4 space-y-2">
          <button
            v-for="item in navItems"
            :key="item.key"
            :class="`block w-full text-left px-4 py-2 rounded-md ${
              activeSection === item.key
                ? 'bg-[#42b883]/10 text-[#42b883] font-semibold'
                : 'text-gray-600 hover:bg-gray-100 hover:text-gray-900'
            }`"
            @click="handleSectionChange(item.key)"
          >
            {{ item.label }}
          </button>

          <!-- Link to React version in mobile menu -->

          <a
            href="https://jensvanherp.be"
            class="block w-full text-center px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 transition-colors"
          >
            React Version
          </a>
        </div>
      </div>
    </div>
  </nav>
</template>
