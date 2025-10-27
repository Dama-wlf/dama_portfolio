<template>
  <section id="projects" class="py-20 bg-white dark:bg-gray-800 transition-colors duration-300">
    <div class="container mx-auto px-4 sm:px-6">
      <h2 class="text-4xl font-bold text-center text-gray-900 dark:text-white mb-4 animate-fade-in">
        Mes Projets
      </h2>
      
      <p class="text-center text-gray-600 dark:text-gray-300 mb-12 max-w-2xl mx-auto animate-fade-in">
        Une sélection de mes réalisations récentes
      </p>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="(project, index) in projects" 
          :key="project.id"
          class="bg-gray-50 dark:bg-gray-900 rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-500 group cursor-pointer transform hover:scale-105 animate-slide-up"
          :style="`animation-delay: ${index * 0.1}s`"
          
        >
          <!-- Image du projet -->
          <div class="h-48 bg-gradient-to-br from-primary-500 to-purple-600 relative overflow-hidden">
            <div class="absolute inset-0 bg-black/0 group-hover:bg-black/20 transition-colors duration-300 flex items-center justify-center">
             
            </div>
          </div>
          
          <!-- Contenu -->
          <div class="p-6">
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2 group-hover:text-primary-600 dark:group-hover:text-primary-400 transition-colors">
              {{ project.title }}
            </h3>
            
            <p class="text-gray-600 dark:text-gray-300 mb-4 line-clamp-2">
              {{ project.description }}
            </p>
            
           
            
           
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const projects = [
  {
    id: 1,
    title: 'Application Web SCRUMORA',
    description: 'Plateforme web de géstion de projets avec méthodologie Scrum, intégrant gestion des tâches',
   
  },
  {
    id: 2,
    title: 'Application de gestion scolaire',
    description: "Création d’une application web pour la gestion administrative d’un établissement scolaire",
   
  },
  {
    id: 3,
    title: 'Application Mobile E-Karama',
    description: "Développement d'une application mobile innovante facilitant la recherche d'offres d'emploi pour les utilisateurs",
   
  },
  {
    id: 4,
    title: "Site web de réservetion d'Hôtel",
    description: "Conception et mise en œuvre d'une plateforme de réservation d'hôtels en ligne.",
   
  },
  
  {
    id: 5,
    title: 'Application de traduction Anglais - Malgache',
    description: "Conception et développement d'une application dédiée à la traduction entre l'anglais et le malgache",
   
  },
  {
    id: 6,
    title: "Application desktop d'extraction de mots-clés",
    description: "Une application desktop permettant de rechercher un mot-clé dans un texte et d’en extraire le mot essentiel",
  
  }
]
</script>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>