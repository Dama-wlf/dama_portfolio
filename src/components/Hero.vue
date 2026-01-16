<template>
  <section id="home" class="min-h-screen flex items-center justify-center pt-16 bg-gradient-to-br from-gray-50 via-blue-50 to-indigo-100 dark:from-gray-900 dark:via-blue-900/20 dark:to-indigo-900/20 relative overflow-hidden">
    <!-- Background decoration -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="absolute -top-40 -right-32 w-80 h-80 bg-primary-500/10 rounded-full blur-3xl animate-float"></div>
      <div class="absolute -bottom-40 -left-32 w-80 h-80 bg-purple-500/10 rounded-full blur-3xl animate-float" style="animation-delay: 1.5s;"></div>
    </div>
    
    <div class="container mx-auto px-4 sm:px-6 relative z-10">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        <!-- Texte -->
        <div class="text-center lg:text-left space-y-6 animate-slide-in-left">
          <div class="space-y-4">
            <h1 class="text-4xl sm:text-5xl lg:text-6xl xl:text-7xl font-bold text-gray-900 dark:text-white leading-tight">
              Bonjour, je suis 
              <span class="gradient-text block">
                TINA Anil Dama
              </span>
            </h1>
            
            <p class="text-xl sm:text-2xl text-gray-600 dark:text-gray-300 leading-relaxed max-w-2xl">
              Développeur <span class="text-primary-600 dark:text-primary-400 font-semibold">Full Stack</span> passionné par la création d'expériences web modernes
            </p>
          </div>

          <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
            <button class="group relative bg-primary-500 text-white px-8 py-4 rounded-xl font-semibold hover:bg-primary-600 transition-all duration-300 shadow-lg hover:shadow-xl transform hover:scale-105 overflow-hidden">
              <a href="#projects" class="relative z-10"> Voir mes projets</a>
              <div class="absolute inset-0 bg-gradient-to-r from-primary-600 to-purple-600 transform scale-x-0 group-hover:scale-x-100 transition-transform duration-300 origin-left"></div>
            </button>
            <button class="group border-2 border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 px-8 py-4 rounded-xl font-semibold hover:border-primary-500 dark:hover:border-primary-400 transition-all duration-300 transform hover:scale-105">
              <a href="/src/assets/CV_TINA_Anil_Dama.pdf" class="relative">Télécharger CV</a>
            </button>
          </div>
        </div>

        <!-- Photo de profil -->
        <div class="relative flex justify-center lg:justify-end animate-slide-up">
          <div class="relative">
            <!-- Cercle décoratif -->
            <div class="absolute inset-0 bg-gradient-to-r from-primary-500 to-purple-600 rounded-full blur-lg opacity-30 animate-pulse-slow"></div>
            
            <!-- Container photo -->
            <div class="relative w-64 h-64 sm:w-80 sm:h-80 rounded-full bg-white dark:bg-gray-800 p-2 shadow-2xl transform hover:scale-105 transition-transform duration-500">
              <img 
                src="/src/assets/anil.JPG" 
                alt="TINA Anil Dama"
                class="w-full h-full rounded-full object-cover border-4 border-white dark:border-gray-800"
              />
            </div>
            
            <!-- Badge animé -->
            <div class="absolute -bottom-4 -right-4 bg-gradient-to-r from-primary-500 to-purple-600 text-white px-4 py-2 rounded-full font-semibold shadow-lg animate-bounce-gentle">
              🚀 Disponible
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Aucune logique nécessaire pour le moment
</script>