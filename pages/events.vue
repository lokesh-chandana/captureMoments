<template>
  <div class="px-4 md:px-16 py-10 space-y-10">
    <h2 class="text-2xl font-bold">Events</h2>

    <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6">
      <div
        v-for="event in paginatedEvents"
        :key="event.title"
        class="space-y-2"
      >
        <img
          :src="event.image"
          class="rounded-lg w-full h-[140px] object-cover"
          alt="Event image"
        />
        <div>
          <h3 class="text-sm font-semibold">{{ event.title }}</h3>
          <p class="text-xs text-gray-500 leading-snug">
            {{ event.description }}
          </p>
        </div>
      </div>
    </div>

    <!-- Pagination -->
    <div
      v-if="totalPages > 1"
      class="flex justify-center items-center gap-2 pt-6 text-sm"
    >
      <button
        :disabled="currentPage === 1"
        @click="currentPage--"
        class="px-2 py-1 text-xl rounded-full hover:bg-gray-100 disabled:text-gray-400"
      >
        ‹
      </button>

      <button
        v-for="page in totalPages"
        :key="page"
        @click="currentPage = page"
        :class="[
          'w-8 h-8 rounded-full flex items-center justify-center',
          currentPage === page
            ? 'bg-gray-800 text-white font-semibold'
            : 'hover:bg-gray-200'
        ]"
      >
        {{ page }}
      </button>

      <button
        :disabled="currentPage === totalPages"
        @click="currentPage++"
        class="px-2 py-1 text-xl rounded-full hover:bg-gray-100 disabled:text-gray-400"
      >
        ›
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const events = ref([
  {
    title: 'Elegant Wedding',
    description: 'A beautiful wedding ceremony with stunning floral arrangements.',
    image: 'https://images.unsplash.com/photo-1531058020387-3be344556be6?fit=crop&w=600&q=80'
  },
  {
    title: 'Rock Concert',
    description: 'An energetic rock concert with a vibrant crowd.',
    image: 'https://images.unsplash.com/photo-1507874457470-272b3c8d8ee2?fit=crop&w=600&q=80'
  },
  {
    title: 'Birthday Party',
    description: 'A fun-filled birthday party with games and laughter.',
    image: 'https://images.unsplash.com/photo-1531058020387-3be344556be6?fit=crop&w=600&q=80'
  },
  {
    title: 'Corporate Event',
    description: 'A professional corporate event with keynote speakers.',
    image: 'https://images.unsplash.com/photo-1531058020387-3be344556be6?fit=crop&w=600&q=80'
  },
  {
    title: 'Cultural Festival',
    description: 'A vibrant celebration of culture, dance, and traditions.',
    image: 'https://images.unsplash.com/photo-1531058020387-3be344556be6?fit=crop&w=600&q=80'
  },
  {
    title: 'Charity Gala',
    description: 'An elegant gala night for fundraising and awareness.',
    image: 'https://images.unsplash.com/photo-1531058020387-3be344556be6?fit=crop&w=600&q=80'
  }
])

const currentPage = ref(1)
const perPage = 5

const totalPages = computed(() =>
  Math.ceil(events.value.length / perPage)
)

const paginatedEvents = computed(() => {
  const start = (currentPage.value - 1) * perPage
  return events.value.slice(start, start + perPage)
})
</script>
