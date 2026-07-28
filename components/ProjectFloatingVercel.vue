<template>
  <section
    class="relative w-full min-h-screen flex flex-col items-center py-10 gap-12 overflow-hidden font-[Barlow]" >
    <!-- Fondo -->
    <div class="absolute inset-0 bg-gradient-to-br from-gray-100 to-white opacity-10"></div>

    <!-- Título -->
    <h2
      class="relative z-10 mt-8 text-3xl md:text-5xl font-extrabold tracking-tight text-center" >
      Desarrollos en GitHub
    </h2>

    <!-- Cards -->
    <div
      class="relative z-10 w-full
             flex flex-col md:flex-row flex-wrap
             justify-center items-stretch md:items-center
             gap-8 px-0 md:px-6"
    >
      <CardProject
        v-for="project in projects"
        :key="project.title"
        :project="project"
      />
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

import CardProject from '@/components/projects/CardProject.vue'

const openLink = (url) => {
  window.open(url, '_blank')
}

const projects = ref([
  {
    title: 'Toolpilot Email',
    tech: 'Next js •  Boomlify• Tailwind',
    description: 'Aplicación web de correos temporales que genera emails desechables usando la API de Boomlify.',
    image: '/images/toolpilot.png',
    link: 'https://toolpilot-two.vercel.app/'
  },
  {
    title: 'AURA 2 - Construccio..',
    tech: 'HTML •  JS • Tailwind',
    description: 'Landing page, sitio web para proyectos de construccion y diseño de infraestructura.',
    image: '/images/construccion2.png',
    link: 'https://aura-2-eta.vercel.app/'
  },
  {
    title: 'AURA - Construcciones',
    tech: 'HTML •  JS • Tailwind',
    description: 'Landing page, sitio web para proyectos de construccion y diseño de infraestructura.',
    image: '/images/construccion.png',
    link: 'https://arquitectura-aura-template.vercel.app/'
  },
  {
    title: 'NexaFlow Saas',
    tech: 'Nuxt JS • Tailwind',
    description: 'Landing page, SaaS para startups, diseño minimalista.',
    image: '/images/nexa.PNG',
    link: 'https://landing-page-saa-s.vercel.app/'
  },
  {
    title: 'TolimaMagico • Planes Turisticos',
    tech: 'Nuxt JS • Tailwind',
    description: 'Landing page dedicada a la atención de clientes, para el sector turístico..',
    image: '/images/tolima.png',
    link: 'https://tolima-magico.vercel.app/'
  },
  {
    title: 'Aurora Hotel',
    tech: 'React JS • Tailwind',
    description: 'Página web hotelera con diseño moderno y minimalista.',
    image: '/images/movil-aurora.PNG',
    link: 'https://hotel-aurora-front.vercel.app/'
  },
  {
    title: 'DeUna Tienda',
    tech: 'React JS • Tailwind',
    description: 'Tienda de servicios y eventos con enfoque comercial.',
    image: '/images/44.PNG',
    link: 'https://store-services-rho.vercel.app/'
  },
  {
    title: 'Ebook LandingPage',
    tech: 'Nuxt JS • Tailwind',
    description: 'Landing page, informacion de libro exclusivo.',
    image: '/images/ebook.PNG',
    link: 'https://ebook-six-rho.vercel.app/'
  },
  {
    title: '3D LandingPage',
    tech: 'Nuxt JS • Tailwind',
    description: 'Landing page, con servicios de desarrollo 3d - Impresion 3D.',
    image: '/images/3drules.PNG',
    link: 'https://3druleswa.vercel.app/'
  }

])
</script>

<style scoped>
@keyframes pulse-slow {
  0%, 100% { opacity: 0.5 }
  50% { opacity: 0.8 }
}
</style>
