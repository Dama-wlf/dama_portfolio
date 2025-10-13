<template>
  <header class="fixed w-full bg-white/80 dark:bg-gray-900/80 backdrop-blur-lg z-50 border-b border-gray-200 dark:border-gray-800 transition-all duration-300">
    <nav class="container mx-auto px-4 sm:px-6 py-4">
      <div class="flex justify-between items-center">
        <!-- Logo -->
        <router-link to="/" class="text-2xl font-bold text-primary-600 dark:text-primary-400 transition-colors hover:scale-105">
          TINA Anil Dama
        </router-link>
        
        <!-- Navigation Desktop -->
        <div class="hidden md:flex space-x-8">
          <a 
            v-for="item in navItems" 
            :key="item.name" 
            :href="item.href"
            class="text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-all duration-300 font-medium relative group"
          >
            {{ item.name }}
            <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-primary-600 group-hover:w-full transition-all duration-300"></span>
          </a>
        </div>
        
        <!-- Mobile menu button -->
        <button 
          @click="isMobileMenuOpen = !isMobileMenuOpen"
          class="md:hidden p-2 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors"
        >
          <div class="w-6 h-6 flex flex-col justify-center space-y-1">
            <span 
              class="block h-0.5 w-6 bg-gray-700 dark:bg-gray-300 transition-all duration-300"
              :class="isMobileMenuOpen ? 'rotate-45 translate-y-1.5' : ''"
            ></span>
            <span 
              class="block h-0.5 w-6 bg-gray-700 dark:bg-gray-300 transition-all duration-300"
              :class="isMobileMenuOpen ? 'opacity-0' : 'opacity-100'"
            ></span>
            <span 
              class="block h-0.5 w-6 bg-gray-700 dark:bg-gray-300 transition-all duration-300"
              :class="isMobileMenuOpen ? '-rotate-45 -translate-y-1.5' : ''"
            ></span>
          </div>
        </button>
      </div>
      
      <!-- Mobile Menu -->
      <div 
        v-if="isMobileMenuOpen"
        class="md:hidden absolute top-full left-0 w-full bg-white/95 dark:bg-gray-900/95 backdrop-blur-lg border-b border-gray-200 dark:border-gray-800 animate-slide-up"
      >
        <div class="container mx-auto px-4 py-4 flex flex-col space-y-4">
          <a 
            v-for="item in navItems" 
            :key="item.name" 
            :href="item.href"
            @click="isMobileMenuOpen = false"
            class="text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors py-2 font-medium"
          >
            {{ item.name }}
          </a>
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const navItems = [
  { name: 'Accueil', href: '#home' },
  { name: 'À propos', href: '#about' },
  { name: 'Compétences', href: '#skills' },
  { name: 'Projets', href: '#projects' },
  { name: 'Contact', href: '#contact' }
]
</script>