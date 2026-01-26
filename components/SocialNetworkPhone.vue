<template>
  <!-- SOLO MÓVIL -->
  <div
    class="fixed top-26 right-0 z-50
           flex flex-col gap-2
           md:hidden"
  >
    <a
      v-for="social in socials"
      :key="social.name"
      :href="social.url"
      target="_blank"
      rel="noopener"
      class="group"
    >
      <div
        class="w-10 h-10
               rounded-xl
               flex items-center justify-center
               shadow-md
               transition-all duration-300
               active:scale-95"
        :class="social.bg"
      >
        <svg
          viewBox="0 0 24 24"
          fill="currentColor"
          class="w-5 h-5 text-white"
        >
          <path :d="social.path" />
        </svg>
      </div>
    </a>
  </div>
</template>

<script setup>
const socials = [
  {
    name: 'YouTube',
    url: 'https://youtube.com',
    bg: 'bg-red-500',
    path: 'M23.5 6.2s-.2-1.6-.9-2.3c-.9-.9-1.9-.9-2.4-1C16.9 2.5 12 2.5 12 2.5s-4.9 0-8.2.4c-.5.1-1.5.1-2.4 1-.7.7-.9 2.3-.9 2.3S0 8.1 0 10v1.9c0 1.9.5 3.8.5 3.8s.2 1.6.9 2.3c.9.9 2.1.9 2.6 1 1.9.2 8 .4 8 .4s4.9 0 8.2-.4c.5-.1 1.5-.1 2.4-1 .7-.7.9-2.3.9-2.3s.5-1.9.5-3.8V10c0-1.9-.5-3.8-.5-3.8zM9.5 14.7V7.9l6.2 3.4-6.2 3.4z'
  },
  {
    name: 'Facebook',
    url: 'https://facebook.com',
    bg: 'bg-blue-600',
    path: 'M22.7 0H1.3C.6 0 0 .6 0 1.3v21.3C0 23.4.6 24 1.3 24h11.5v-9.3H9.7V11h3.1V8.4c0-3.1 1.9-4.8 4.7-4.8 1.3 0 2.4.1 2.7.1v3.2h-1.9c-1.5 0-1.8.7-1.8 1.8V11h3.6l-.5 3.7h-3.1V24h6.1c.7 0 1.3-.6 1.3-1.3V1.3C24 .6 23.4 0 22.7 0z'
  },
  {
    name: 'WhatsApp',
    url: 'https://wa.me/573000000000',
    bg: 'bg-green-500',
    path: 'M12 0a12 12 0 00-10.3 18.1L0 24l6.1-1.6A12 12 0 1012 0z'
  }
]
</script>
