<script setup lang="ts">
import { ref } from 'vue'

const showDogModal = ref(false)
</script>

<template>
  <div class="bg-white rounded-lg shadow-md p-8">
    <h2 class="text-3xl font-bold text-gray-800 mb-8">About Me</h2>

    <div class="grid md:grid-cols-2 gap-8">
      <!-- Who I am -->
      <div>
        <h3 class="text-xl font-semibold text-gray-800 mb-4">Who I am</h3>
        <p class="text-gray-600 mb-4">
          I'm a passionate developer with experience in building modern web applications. I enjoy
          solving complex problems and creating user-friendly solutions.
        </p>
        <p class="text-gray-600">
          When I'm not coding, you can find me walking my
          <button @click="showDogModal = true" class="text-[#42b883] hover:underline font-semibold">
            dog</button
          >, swimming or on a trip with my significant other.
        </p>
      </div>

     <!-- Quick Facts -->
<div>
  <h3 class="text-xl font-semibold text-gray-800 mb-4">Quick Facts</h3>
  <ul class="space-y-2 text-gray-600">
    <li class="flex items-center">
      <span class="font-medium w-24">Location:</span>
      <span>Jette, Belgium</span>
    </li>
    <li class="flex items-center">
      <span class="font-medium w-24">Email:</span>
      <span>info@jensvanherp.be</span>
    </li>
    <li class="flex items-center">
      <span class="font-medium w-24">Languages:</span>
      <span>Dutch, English</span>
    </li>
  </ul>
</div>

    <div
      v-if="showDogModal"
      class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
      @click="showDogModal = false"
    >
      <div class="bg-white rounded-lg p-8 max-w-md relative" @click.stop>
        <button
          @click="showDogModal = false"
          class="absolute top-4 right-4 text-gray-500 hover:text-gray-700 text-2xl"
        >
          ×
        </button>
        <h3 class="text-2xl font-bold text-gray-800 mb-4">Meet Arthur!</h3>
        <img src="/dog.jpg" alt="My dog" class="w-full rounded-lg mb-4" />
      </div>
    </div>
  </div>
</template>
