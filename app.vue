<script setup>
import { useHead } from '#app'

useHead({
  title: 'Mileer león',
  link: [
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Barlow:wght@400;700&display=swap'
    },
    {
      rel: 'icon',
      type: 'image/png',
      href: 'https://img.icons8.com/ios_filled/1200/circled-m.jpg'
    },
    {
      rel: 'shortcut icon',
      href: 'https://img.icons8.com/ios_filled/1200/circled-m.jpg'
    },
  ],
  meta: [
    { name: 'description', content: 'Mileer león is an developer, designer and  based in Ibagué, Tolima Colombia.' },
    { name: 'viewport-fit', content: 'cover' },
    
    // Open Graph tags
    { property: 'og:title', content: 'Mileer león' },
    { property: 'og:description', content: 'Mileer león is an developer, designer and  based in Ibagué, Tolima Colombia.' },
    { property: 'og:type', content: 'website' },
    { property: 'og:locale', content: 'en_US' },
    { property: 'og:image', content: 'https://cdn.sanity.io/images/3vte03iz/production/1f882da531be0b0075383493d5b45e55c88fceef-1200x651.png?rect=0,1,1200,650&w=1200&h=650&auto=format' },
    { property: 'og:image:width', content: '1200' },
    { property: 'og:image:height', content: '650' },

    // Twitter Card tags
    { name: 'twitter:card', content: 'summary_large_image' },
    { name: 'twitter:image', content: 'https://cdn.sanity.io/images/3vte03iz/production/1f882da531be0b0075383493d5b45e55c88fceef-1200x651.png?rect=0,1,1200,650&w=1200&h=650&auto=format' },
    { name: 'twitter:image:width', content: '1200' },
    { name: 'twitter:image:height', content: '650' },
  ]
})
</script>

<template>
  <NuxtPage />
</template>

