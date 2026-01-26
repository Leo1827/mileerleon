<template>
  <div class="min-h-screen flex flex-col">
    <Header />
    <ProjectFloating />
    <ProjectFloatingVercel />
    <ServicesSection />
    <ContactForm />
    <ScrollTop />
    <Footer />
    <ThemeToggle />
  </div>
</template>

<script setup>
  import Header from '@/components/Header.vue'
  import ProjectFloating from '@/components/ProjectFloating.vue'
  import ProjectFloatingVercel from '@/components/ProjectFloatingVercel.vue'
  import ServicesSection from '@/components/services/ServicesSection.vue'
  import ContactForm from '@/components/ContactForm.vue'
  import ScrollTop from '@/components/ScrollTop.vue'
  import Footer from '@/components/Footer.vue'
  import ThemeToggle from '@/components/ThemeToggle.vue'
</script>
