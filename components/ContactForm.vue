<template>
  <section class="max-w-3xl mx-auto px-6 py-24 relative">
    <!-- TÍTULO -->
    <h2 class="my-8 text-3xl md:text-5xl font-extrabold tracking-tight text-center">
      Contacto
    </h2>

    <p class="text-center text-gray-500 mb-12">
      ¿Tienes un proyecto o necesitas un servicio?
      Escríbeme y te responderé lo antes posible.
    </p>

    <!-- FORMULARIO -->
    <form
      @submit.prevent="submitForm"
      class="rounded-2xl p-8 sm:p-10
             shadow-[0_20px_50px_rgba(0,0,0,0.08)]
             space-y-6 "
    >
      <!-- NOMBRE -->
      <div>
        <label class="block text-sm font-medium mb-2">Nombre</label>
        <input
          v-model="form.name"
          type="text"
          required
          placeholder="Tu nombre"
          class="w-full rounded-lg border border-gray-400
                 px-4 py-3 text-sm
                 focus:outline-none focus:ring-2 focus:ring-black"
        />
      </div>

      <!-- EMAIL -->
      <div>
        <label class="block text-sm font-medium mb-2">Correo electrónico</label>
        <input
          v-model="form.email"
          type="email"
          required
          placeholder="correo@ejemplo.com"
          class="w-full rounded-lg border border-gray-400
                 px-4 py-3 text-sm
                 focus:outline-none focus:ring-2 focus:ring-black"
        />
      </div>

      <!-- TELÉFONO -->
      <div>
        <label class="block text-sm font-medium mb-2">Teléfono</label>
        <input
          v-model="form.phone"
          type="tel"
          placeholder="323 000 0000"
          class="w-full rounded-lg border border-gray-400
                 px-4 py-3 text-sm
                 focus:outline-none focus:ring-2 focus:ring-black"
        />
      </div>

      <!-- MENSAJE -->
      <div>
        <label class="block text-sm font-medium mb-2">Mensaje</label>
        <textarea
          v-model="form.message"
          rows="5"
          required
          placeholder="Cuéntame sobre tu proyecto o necesidad"
          class="w-full rounded-lg border border-gray-400
                 px-4 py-3 text-sm resize-none
                 focus:outline-none focus:ring-2 focus:ring-black"
        />
      </div>

      <!-- BOTÓN -->
      <button
        type="submit"
        :disabled="loading"
        class="w-full rounded-lg bg-black text-white
               py-3 font-medium
               hover:opacity-90 transition
               disabled:opacity-50"
      >
        {{ loading ? 'Enviando…' : 'Enviar mensaje' }}
      </button>
    </form>

    <!-- MODAL CONFIRMACIÓN -->
    <Transition name="modal">
      <div
        v-if="success"
        class="fixed inset-0 z-50 flex items-center justify-center"
      >
        <!-- OVERLAY -->
        <div
          class="absolute inset-0 bg-black/40 backdrop-blur-sm"
          @click="closeModal"
        ></div>

        <!-- MODAL -->
        <div
          class="relative bg-white rounded-2xl px-8 py-10
                 w-full max-w-sm mx-4
                 shadow-[0_30px_80px_rgba(0,0,0,0.25)]"
        >
          <!-- ICONO -->
          <div
            class="w-12 h-12 mx-auto mb-4
                   rounded-full bg-black text-white
                   flex items-center justify-center text-lg"
          >
            ✓
          </div>

          <h3 class="text-xl font-semibold text-center mb-2">
            Mensaje enviado
          </h3>

          <p class="text-sm text-gray-500 text-center mb-6">
            Gracias por contactarme.  
            Te responderé lo antes posible.
          </p>

          <button
            @click="closeModal"
            class="w-full rounded-lg bg-black text-white
                   py-2.5 text-sm font-medium
                   hover:opacity-90 transition"
          >
            Cerrar
          </button>
        </div>
      </div>
    </Transition>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'

const loading = ref(false)
const success = ref(false)

const form = reactive({
  name: '',
  email: '',
  phone: '',
  message: '',
})

const submitForm = async () => {
  loading.value = true

  try {
    const response = await fetch('https://formspree.io/f/xeeejagg', {
      method: 'POST',
      headers: {
        'Accept': 'application/json',
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(form),
    })

    if (response.ok) {
      success.value = true
      Object.keys(form).forEach(k => (form[k] = ''))

      // cierre automático (opcional)
      setTimeout(() => {
        success.value = false
      }, 4000)
    }
  } catch (error) {
    alert('Error al enviar el mensaje.')
  } finally {
    loading.value = false
  }
}

const closeModal = () => {
  success.value = false
}
</script>

<style scoped>
.modal-enter-active,
.modal-leave-active {
  transition: all 0.3s ease;
}
.modal-enter-from {
  opacity: 0;
  transform: scale(0.95);
}
.modal-leave-to {
  opacity: 0;
  transform: scale(0.95);
}
</style>
