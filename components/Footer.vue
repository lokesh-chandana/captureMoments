<template>
  <footer class="bg-white text-gray-400 text-sm py-8">
    <div class="max-w-4xl mx-auto px-4 flex flex-col items-center space-y-6">

      <!-- Top links -->
      <div class="flex space-x-12">
        <NuxtLink to="/privacyPolicy" class="hover:text-gray-600 transition">Privacy Policy</NuxtLink>
        <NuxtLink to="/termsOfService" class="hover:text-gray-600 transition">Terms Of Service</NuxtLink>
        <NuxtLink to="/contactUs" class="hover:text-gray-600 transition">Contact Us</NuxtLink>
      </div>

      <!-- Social media icons -->
      <div class="flex space-x-6">
        <!-- Instagram -->
        <a href="#" class="hover:text-gray-600 transition">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"
              d="M7.75 3h8.5A4.75 4.75 0 0121 7.75v8.5A4.75 4.75 0 0116.25 21h-8.5A4.75 4.75 0 013 16.25v-8.5A4.75 4.75 0 017.75 3zM15 11.25a3 3 0 11-6 0 3 3 0 016 0zm2.25-4.5h.008v.008h-.008V6.75z" />
          </svg>
        </a>

        <!-- Twitter -->
        <a href="#" class="hover:text-gray-600 transition">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M22.46 6c-.77.35-1.6.58-2.46.69a4.3 4.3 0 001.88-2.37 8.66 8.66 0 01-2.73 1.04A4.27 4.27 0 0016.11 4c-2.37 0-4.29 1.92-4.29 4.29 0 .34.04.68.11 1A12.13 12.13 0 013 5.15a4.28 4.28 0 001.32 5.71 4.22 4.22 0 01-1.94-.54v.05c0 2.01 1.43 3.69 3.33 4.07-.35.1-.72.15-1.1.15-.27 0-.53-.03-.78-.07a4.29 4.29 0 004 2.97 8.58 8.58 0 01-6.33 1.77A12.08 12.08 0 008.29 21c7.55 0 11.68-6.26 11.68-11.68 0-.18-.01-.35-.02-.53A8.34 8.34 0 0022.46 6z" />
          </svg>
        </a>

        <!-- Facebook -->
        <a href="#" class="hover:text-gray-600 transition">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.99 3.66 9.12 8.44 9.88v-6.99H7.9v-2.89h2.54V9.41c0-2.5 1.49-3.89 3.77-3.89 1.09 0 2.23.2 2.23.2v2.45h-1.25c-1.23 0-1.61.76-1.61 1.54v1.85h2.75l-.44 2.89h-2.31v6.99C18.34 21.12 22 16.99 22 12z" />
          </svg>
        </a>
      </div>

      <!-- Copyright -->
      <p class="text-xs text-gray-400">
        ©2025 Capture Moments. All rights reserved.
      </p>

    </div>
  </footer>
</template>
