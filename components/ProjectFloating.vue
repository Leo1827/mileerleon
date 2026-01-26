<template>
  <section
    class="relative w-full min-h-screen flex flex-col mt-8 md:pb-0 pb-10 justify-center items-center gap-10 overflow-hidden font-[Barlow]"
  >

    <!-- Título principal -->
    <h2 class="text-3xl md:text-5xl font-extrabold z-10 tracking-tight text-center ">
      Proyectos en producción
    </h2>

    <!-- Contenedor de tarjetas -->
    <div
      class="flex flex-col md:flex-row flex-wrap justify-center items-center gap-10 z-10 px-4 md:px-0"
    >
      <div
        v-for="(project, index) in projects"
        :key="index"
        class="group relative w-full md:w-64 h-auto md:h-80 bg-white md:bg-opacity-100 bg-opacity-60 backdrop-blur-md rounded-3xl shadow-xl hover:shadow-2xl transition-all duration-500 transform md:hover:-translate-y-3 md:hover:rotate-2 hover:scale-[1.02]"
        :style="getFloatingStyle(index)"
      >
        <!-- Decoración artística en mobile -->
        <div
          class="absolute -top-4 -left-4 w-16 h-16 bg-gradient-to-br from-blue-300 to-indigo-400 rounded-full blur-xl opacity-30 md:hidden"
        ></div>
        <div
          class="absolute -bottom-4 -right-4 w-20 h-20 bg-gradient-to-tr from-pink-300 to-yellow-300 rounded-full blur-2xl opacity-30 md:hidden"
        ></div>

        <!-- Imagen -->
        <img
          :src="project.image"
          :alt="project.title"
          class="w-full h-48 md:h-1/2 object-cover rounded-t-3xl"
        />

        <!-- Contenido -->
        <div class="p-6 text-left relative z-10">
          <h3
            class="text-2xl md:text-lg font-extrabold text-gray-800 mb-2 md:mb-1 drop-shadow-sm"
          >
            {{ project.title }}
          </h3>
          <p class="text-sm md:text-xs text-gray-500 mb-3 italic">
            {{ project.tech }}
          </p>
          <p class="text-base md:text-sm text-gray-700 leading-snug line-clamp-none md:line-clamp-3">
            {{ project.description }}
          </p>
        </div>

        <!-- Enlace -->
        <div class="pb-4 pl-6">
          <a
            :href="project.link"
            target="_blank"
            class="inline-block mt-2 text-xs md:text-[10px] font-semibold tracking-wider text-blue-600 hover:text-indigo-700 transition"
          >
            → VER PROYECTO
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Lista de proyectos
const projects = ref([
  {
    title: 'Canhoto Premium',
    tech: 'Laravel • Tailwind • JS • MySQL',
    description:
      'Tienda online con acceso a subscripción, vinos exclusivos, facturación, inventario, panel administrador, responsive.',
    image: '/images/1111.PNG',
    link: 'https://canhotopremium.com/'
  },
  {
    title: 'Canhoto Black',
    tech: 'PHP • HTML • Tailwind • JS',
    description:
      'Landing page, formularios con Mailer y manejo de rendimiento con pixie Facebook.',
    image: '/images/22.PNG',
    link: 'https://www.canhotoblack.com/'
  }
])

// Movimiento sutil
const getFloatingStyle = (index) => {
  const offset = (index % 2 === 0 ? 1 : -1) * (5 + index * 2)
  const animation = `float-${index % 3}`
  return {
    animation: `${animation} 6s ease-in-out infinite`,
    transform: `translateY(${offset}px)`
  }
}
</script>

<style scoped>
@keyframes float-0 {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
}
@keyframes float-1 {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(8px);
  }
}
@keyframes float-2 {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-12px);
  }
}

/* Animación de fondo sutil */
@keyframes pulse-slow {
  0%, 100% {
    opacity: 0.5;
  }
  50% {
    opacity: 0.8;
  }
}
</style>
