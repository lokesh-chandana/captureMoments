<template>
  <section class="max-w-4xl mx-auto px-4 py-16 text-gray-800">
    <h1 class="text-3xl font-bold mb-10">Photography Services</h1>

    <div class="space-y-12">
      <div v-for="service in services" :key="service.title">
        <h2 class="text-lg font-semibold mb-2">{{ service.title }}</h2>
        <p class="mb-4">{{ service.description }}</p>
        <button
          class="bg-gray-100 px-5 py-2 rounded-full text-sm font-semibold hover:bg-gray-200 transition cursor-pointer"
          @click="openModal(service.title)"
        >
          Request a Quote
        </button>
      </div>
    </div>

    <div v-if="showModal" class="fixed inset-0 bg-gray-200 bg-opacity-60 flex items-center justify-center z-50">
      <div class="bg-white p-6 rounded-lg max-w-md w-full shadow-xl relative">
        <button @click="closeModal" class="absolute top-3 right-3 text-gray-500 hover:text-black cursor-pointer">&times;</button>
        <h2 class="text-xl font-semibold mb-4">Request a Quote - {{ selectedService }}</h2>
        <form class="space-y-4">
          <input
            type="text"
            placeholder="Your Name"
            class="w-full border border-gray-300 rounded-md px-4 py-2 focus:outline-none focus:ring-2 focus:ring-black"
          />
          <input
            type="email"
            placeholder="Your Email"
            class="w-full border border-gray-300 rounded-md px-4 py-2 focus:outline-none focus:ring-2 focus:ring-black"
          />
          <textarea
            rows="4"
            placeholder="Your Message"
            class="w-full border border-gray-300 rounded-md px-4 py-2 focus:outline-none focus:ring-2 focus:ring-black"
          ></textarea>
          <button
            type="submit"
            class="bg-black text-white px-5 py-2 rounded-full hover:bg-gray-800 transition cursor-pointer"
          >
            Send
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const showModal = ref(false)
const selectedService = ref('')

const services = [
  {
    title: 'Portrait Photography',
    description:
      'Capture the essence of your personality with professional portrait photography. Whether you need a headshot for your professional profile or a personal portrait, I offer tailored sessions to meet your needs. My approach combines natural light and studio techniques to create stunning images that reflect your unique style.',
  },
  {
    title: 'Wedding Photography',
    description:
      'Celebrate your special day with timeless wedding photography. From intimate ceremonies to grand celebrations, I document every moment with care and creativity. My style is a blend of candid shots and beautifully composed portraits, ensuring your wedding memories are preserved in exquisite detail.',
  },
  {
    title: 'Event Coverage',
    description:
      'Capture the energy and excitement of your event with professional event photography. Whether it\'s a corporate conference, a private party, or a public gathering, I provide comprehensive coverage that tells the story of your event. My focus is on capturing key moments and candid interactions, delivering a visual narrative that you can cherish.',
  },
]

const openModal = (title) => {
  selectedService.value = title
  showModal.value = true
}

const closeModal = () => {
  showModal.value = false
}
</script>
