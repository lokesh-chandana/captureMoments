<template>
  <header class="w-full bg-white shadow-sm">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center space-x-2">
          <svg class="h-6 w-6 text-black" fill="currentColor" viewBox="0 0 24 24">
            <path d="M3 3h7v7H3V3zm11 0h7v7h-7V3zM3 14h7v7H3v-7zm11 0h7v7h-7v-7z" />
          </svg>
          <a href="/">
            <span class="text-lg font-semibold text-black">CaptureLife</span>
          </a>
        </div>

        <nav class="hidden md:flex space-x-8 text-sm font-medium text-gray-700">
          <NuxtLink to="/" class="hover:text-black">Home</NuxtLink>
          <NuxtLink to="/about" class="hover:text-black">About</NuxtLink>
          <NuxtLink to="/services" class="hover:text-black">Services</NuxtLink>
          <NuxtLink to="/events" class="hover:text-black">Events</NuxtLink>
          <NuxtLink to="/contactUs" class="hover:text-black">Contact</NuxtLink>
        </nav>

        <div class="flex items-center space-x-3">
          <button class="p-2 rounded-full bg-gray-100 hover:bg-gray-200">
            <svg class="h-5 w-5 text-gray-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-4.35-4.35m0 0A7 7 0 1010.65 6.65a7 7 0 006.35 10.35z" />
            </svg>
          </button>
          <button class="p-2 rounded-full bg-gray-100 hover:bg-gray-200">
            <svg class="h-5 w-5 text-gray-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" d="M5.121 17.804A11.955 11.955 0 0012 20c2.33 0 4.493-.672 6.243-1.818M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
            </svg>
          </button>
        </div>
      </div>
    </div>
  </header>
</template>
