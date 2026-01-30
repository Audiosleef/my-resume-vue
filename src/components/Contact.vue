<script setup lang="ts">
interface ContactInfo {
  icon: string
  label: string
  value: string
  link: string
}

const contactInfo: ContactInfo[] = [
  {
    icon: '📧',
    label: 'Email',
    value: 'Contact me!',
    link: 'mailto:jensvanherp2012@gmail.com',
  },
  {
    icon: '📍',
    label: 'Location',
    value: 'Jette, Belgium',
    link: '#',
  },
  {
    icon: '💼',
    label: 'LinkedIn',
    value: 'Contact me!',
    link: 'https://www.linkedin.com/in/jens-van-herp-41292a21/',
  },
]
</script>

<template>
  <section id="contact" class="py-16 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4">
      <div class="bg-white rounded-lg shadow-md p-8">
        <h2 class="text-3xl font-bold mb-6 text-gray-800">Contact Me</h2>

        <div class="max-w-2xl mx-auto text-center">
          <h3 class="text-xl font-semibold mb-4 text-gray-700">Get In Touch</h3>
          <p class="text-gray-600 mb-8 text-lg">
            I'm always interested in hearing about new opportunities and exciting projects. Feel
            free to reach out if you'd like to collaborate or just have a chat!
          </p>

          <div class="grid md:grid-cols-3 gap-6">
            <div
              v-for="(item, index) in contactInfo"
              :key="index"
              class="flex flex-col items-center p-6 bg-gray-50 rounded-lg hover:bg-gray-100 transition-colors"
            >
              <span class="text-4xl mb-3">{{ item.icon }}</span>
              <p class="text-sm font-medium text-gray-700 mb-2">{{ item.label }}</p>
              <span v-if="item.link === '#'" class="text-[#42b883] font-medium">{{
                item.value
              }}</span>
              <a
                v-else
                :href="item.link"
                class="text-[#42b883] hover:text-[#35495e] transition-colors font-medium"
                :target="item.link.startsWith('http') ? '_blank' : '_self'"
                rel="noopener noreferrer"
                >{{ item.value }}</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
