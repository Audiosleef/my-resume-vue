<script setup lang="ts">
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="bg-gradient-to-r from-[#2c3e50] to-[#42b883] text-white py-8 mt-8">
    <div class="max-w-6xl mx-auto px-4">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <div class="mb-4 md:mb-0">
          <p class="text-lg font-semibold">Jens Van Herp</p>
          <p class="text-gray-300">Full Stack Developer</p>
        </div>

        <div class="flex space-x-6">
          <a
            href="https://www.linkedin.com/in/jens-van-herp-41292a21/"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-300 hover:text-white transition-colors"
          >
            LinkedIn
          </a>

          <a
            href="mailto:info@jensvanherp.be"
            class="text-gray-300 hover:text-white transition-colors"
          >
            Email
          </a>
        </div>
      </div>

      <div class="border-t border-gray-600 mt-6 pt-6 text-center">
        <p class="text-gray-300 text-sm">
          © {{ currentYear }} Jens Van Herp. Built with Vue.js & Tailwind CSS.
        </p>
      </div>
    </div>
  </footer>
</template>
