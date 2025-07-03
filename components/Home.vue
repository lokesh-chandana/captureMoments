<template>
  <div class="px-4 md:px-8 lg:px-16 py-10 space-y-12">

    <!-- Hero Image -->
    <div class="rounded-xl overflow-hidden">
      <img
        src="https://images.unsplash.com/photo-1501785888041-af3ef285b470?fit=crop&w=1200&q=80"
        alt="Hero Landscape"
        class="w-full h-64 md:h-96 object-cover"
      />
    </div>

    <!-- Featured Work -->
    <section>
      <h2 class="text-xl font-semibold mb-4">Featured Work</h2>
      <div class="grid grid-cols-3 sm:grid-cols-6 gap-4">
        <img
          v-for="(img, i) in featuredImages"
          :key="'featured-' + i"
          :src="img"
          class="rounded-lg object-cover aspect-square cursor-pointer"
          @click="openModal(img)"
        />
      </div>
    </section>

    <!-- Categories -->
    <section>
      <h2 class="text-xl font-semibold mb-4">Categories</h2>
      <div class="flex space-x-6 border-b mb-6 text-gray-600">
        <span
          v-for="category in categories"
          :key="category"
          @click="selectedCategory = category"
          :class="[
            'pb-2 cursor-pointer',
            selectedCategory === category
              ? 'border-b-2 border-black font-medium text-black'
              : 'hover:text-black'
          ]"
        >
          {{ category }}
        </span>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <img
          v-for="(img, i) in categoryImages[selectedCategory]"
          :key="selectedCategory + '-' + i"
          :src="img"
          class="rounded-xl object-cover h-64 w-full cursor-pointer"
          @click="openModal(img)"
        />
      </div>
    </section>

    <!-- Image Modal -->
    <div
      v-if="showModal"
      class="fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50"
      @click.self="closeModal"
    >
      <div class="relative max-w-3xl w-full p-4">
        <button
          class="absolute top-2 right-2 text-white text-xl font-bold"
          @click="closeModal"
        >
          &times;
        </button>
        <img :src="modalImage" class="w-full max-h-[80vh] object-contain rounded-lg shadow-lg" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const featuredImages = [
  "https://images.unsplash.com/photo-1506744038136-46273834b3fb?fit=crop&w=400&q=80",
  "https://images.unsplash.com/photo-1517841905240-472988babdf9?fit=crop&w=400&q=80",
  "https://images.unsplash.com/photo-1593642632823-8f785ba67e45?fit=crop&w=400&q=80",
  "https://images.unsplash.com/photo-1517841905240-472988babdf9?fit=crop&w=400&q=80",
  "https://images.unsplash.com/photo-1593642632823-8f785ba67e45?fit=crop&w=400&q=80",
  "https://images.unsplash.com/photo-1517841905240-472988babdf9?fit=crop&w=400&q=80"
]

const categories = ['Landscapes', 'Portraits', 'Events']
const selectedCategory = ref('Landscapes')

const categoryImages = {
  Landscapes: [
    "https://images.unsplash.com/photo-1517841905240-472988babdf9?fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1523413651479-597eb2da0ad6?fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1502685104226-ee32379fefbe?fit=crop&w=800&q=80"
  ],
  Portraits: [
    "https://images.unsplash.com/photo-1517841905240-472988babdf9?fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1502685104226-ee32379fefbe?fit=crop&w=800&q=80"
  ],
  Events: [
    "https://images.unsplash.com/photo-1531058020387-3be344556be6?fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1502685104226-ee32379fefbe?fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1521334884684-d80222895322?fit=crop&w=800&q=80"
  ]
}

// Modal state
const showModal = ref(false)
const modalImage = ref('')

function openModal(imgUrl) {
  modalImage.value = imgUrl
  showModal.value = true
}

function closeModal() {
  showModal.value = false
}
</script>

<style scoped>
/* optional: disable scroll when modal open */
body.modal-open {
  overflow: hidden;
}
</style>
