<template>
  <header
    class="min-h-screen font-[Barlow] flex flex-col items-center justify-center text-center relative overflow-hidden"
  >
    <div class="absolute top-8">
      <!-- Ubicación y correo -->
      <div
        class="text-xs md:text-sm font-bold  top-1 tracking-wide mb-1"
      >
        IBAGUÉ, COLOMBIA
      </div>
      <div class="text-[10px] md:text-xs text-gray-400 mb-6">
        MILEERDUBANLEON@GMAIL.COM
      </div>

      <!-- Nombre principal -->
      <h1
        class="text-4xl md:text-7xl transform scale-y-110 font-bold md:mt-14 mt-20"
      >
        MILEER LEÓN
      </h1>
    </div>

    <Gallery />

    <!-- Subtítulo -->
    <h2
      class="text-4xl md:text-9xl font-extrabold text-gray-400 mt-16 mb-4"
    >
      DESARROLLADOR
    </h2>

    <div class="absolute bottom-10">
      <!-- Clientes -->
      <p class="text-xs md:text-sm font-semibold text-gray-600 tracking-widest mt-4">
        CLIENTES
      </p>
      <p class="text-[10px] md:text-xs text-gray-400 mt-1">
        ALUMART Panamá, Garrafeira Canhoto, Maquinitas Guadalajara
      </p>
    </div>

  </header>
</template>

<script setup>
import Gallery from '@/components/Gallery.vue'
</script>
