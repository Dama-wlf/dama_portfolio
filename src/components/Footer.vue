<template>
  <footer class="bg-gray-900 text-white py-12 transition-colors duration-300">
    <div class="container mx-auto px-4 sm:px-6">
      <div class="grid md:grid-cols-4 gap-8">
        <!-- Logo et description -->
        <div class="md:col-span-2">
          <h3 class="text-2xl font-bold text-primary-400 mb-4">TINA Anil Dama</h3>
          <p class="text-gray-400 mb-6 max-w-md">
            Développeur Full Stack passionné par la création d'expériences web modernes et performantes.
          </p>
         
        </div>
        
        <!-- Liens rapides -->
        <div>
          <h4 class="text-lg font-semibold mb-4">Liens rapides</h4>
          <div class="space-y-2">
            <a 
              v-for="link in quickLinks" 
              :key="link.name"
              :href="link.href"
              class="block text-gray-400 hover:text-primary-400 transition-colors duration-300"
            >
              {{ link.name }}
            </a>
          </div>
        </div>
        
        <!-- Contact -->
        <div>
          <h4 class="text-lg font-semibold mb-4">Contact</h4>
          <div class="space-y-2 text-gray-400">
            <p>damaanil1504@gmail.com</p>
            <p>+261 32 53 948 38 / +261 34 58 850 81</p>
            <p>Antsirabe, Madagascar</p>
          </div>
        </div>
      </div>
      
      <div class="border-t border-gray-800 mt-8 pt-8 flex flex-col md:flex-row justify-between items-center">
        <p class="text-gray-400 text-sm">
          © {{ new Date().getFullYear() }} damaanil. Tous droits réservés.
        </p>
        
      </div>
    </div>
  </footer>
</template>

<script setup>


const quickLinks = [
  { name: 'Accueil', href: '#home' },
  { name: 'À propos', href: '#about' },
  { name: 'Compétences', href: '#skills' },
  { name: 'Projets', href: '#projects' },
  { name: 'Contact', href: '#contact' }
]
</script>