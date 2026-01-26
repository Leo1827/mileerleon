<template>
  <div
    class="w-[350px] mx-auto md:mx-0 sm:w-[300px] md:w-[260px] h-[380px]
           rounded-3xl overflow-hidden shadow-xl
           bg-black cursor-pointer
           transition-transform duration-500
           hover:-translate-y-2 hover:shadow-2xl"
    @click="openLink(project.link)"
  >
    <div class="relative w-full h-full">
      <img
        :src="project.image"
        :alt="project.title"
        class="w-full h-full object-cover"
      />

      <div
        class="absolute inset-0 flex flex-col justify-end
               bg-gradient-to-t from-black/85 via-black/40 to-transparent
               p-6 text-white"
      >
        <h3 class="text-xl font-extrabold">
          {{ project.title }}
        </h3>

        <p class="text-xs uppercase tracking-widest text-gray-300 mt-1">
          {{ project.tech }}
        </p>

        <p class="text-sm text-gray-200 mt-2 leading-snug">
          {{ project.description }}
        </p>

        <span class="mt-3 text-xs font-semibold tracking-wider text-blue-300">
          VER PROYECTO →
        </span>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  project: {
    type: Object,
    required: true
  }
})

const openLink = (url) => {
  window.open(url, '_blank')
}
</script>
