<template>
  <div class="min-h-screen bg-white dark:bg-gray-900 transition-colors duration-300">
    <Header />
    <router-view />
    <Footer />
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
</script>