<template>
  <div class="pt-20 min-h-screen bg-white dark:bg-gray-900 transition-colors duration-300">
    <div class="container mx-auto px-4 sm:px-6 py-12">
      <!-- Bouton retour -->
      <button 
        @click="$router.back()"
        class="flex items-center text-gray-600 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 mb-8 transition-colors duration-300 group animate-fade-in"
      >
        <span class="text-2xl mr-2 group-hover:-translate-x-1 transition-transform duration-300">←</span>
        Retour aux projets
      </button>

      <!-- Header du projet -->
      <div class="grid lg:grid-cols-2 gap-12 mb-12">
        <!-- Image principale -->
        <div class="animate-slide-in-left">
          <div class="bg-gradient-to-br from-primary-500 to-purple-600 rounded-2xl h-80 lg:h-96 shadow-2xl"></div>
        </div>
        
        <!-- Informations -->
        <div class="animate-slide-in-right">
          <h1 class="text-4xl lg:text-5xl font-bold text-gray-900 dark:text-white mb-4">
            {{ project.title }}
          </h1>
          
          <p class="text-xl text-gray-600 dark:text-gray-300 mb-6 leading-relaxed">
            {{ project.fullDescription }}
          </p>
          
          <!-- Technologies -->
          <div class="mb-8">
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">Technologies utilisées</h3>
            <div class="flex flex-wrap gap-3">
              <span 
                v-for="tech in project.technologies" 
                :key="tech"
                class="px-4 py-2 bg-primary-500/10 text-primary-600 dark:text-primary-400 rounded-full border border-primary-500/20 font-medium"
              >
                {{ tech }}
              </span>
            </div>
          </div>
          
          <!-- Boutons d'action -->
          <div class="flex flex-col sm:flex-row gap-4">
            <a 
              :href="project.demoUrl"
              class="bg-primary-500 text-white px-8 py-4 rounded-xl font-semibold hover:bg-primary-600 transition-all duration-300 transform hover:scale-105 text-center shadow-lg hover:shadow-xl"
            >
              🚀 Voir le projet en ligne
            </a>
            <a 
              :href="project.githubUrl"
              class="border-2 border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 px-8 py-4 rounded-xl font-semibold hover:border-primary-500 dark:hover:border-primary-400 transition-all duration-300 transform hover:scale-105 text-center"
            >
              💻 Code source
            </a>
          </div>
        </div>
      </div>

      <!-- Détails du projet -->
      <div class="grid lg:grid-cols-3 gap-8 mb-12">
        <!-- Objectifs -->
        <div class="lg:col-span-2 animate-fade-in">
          <h2 class="text-3xl font-bold text-gray-900 dark:text-white mb-6">À propos du projet</h2>
          
          <div class="prose prose-lg dark:prose-invert max-w-none">
            <p class="text-gray-600 dark:text-gray-300 mb-6">
              {{ project.details.objectives }}
            </p>
            
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Fonctionnalités principales</h3>
            <ul class="text-gray-600 dark:text-gray-300 space-y-2 mb-6">
              <li v-for="feature in project.details.features" :key="feature" class="flex items-center">
                <span class="w-2 h-2 bg-primary-500 rounded-full mr-3"></span>
                {{ feature }}
              </li>
            </ul>
            
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Défis relevés</h3>
            <p class="text-gray-600 dark:text-gray-300">
              {{ project.details.challenges }}
            </p>
          </div>
        </div>
        
        <!-- Informations techniques -->
        <div class="animate-slide-up">
          <div class="bg-gray-50 dark:bg-gray-800 rounded-2xl p-6 shadow-lg sticky top-24">
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Informations</h3>
            
            <div class="space-y-4">
              <div>
                <span class="text-sm text-gray-500 dark:text-gray-400 block">Client</span>
                <span class="text-gray-900 dark:text-white font-medium">{{ project.details.client }}</span>
              </div>
              
              <div>
                <span class="text-sm text-gray-500 dark:text-gray-400 block">Durée</span>
                <span class="text-gray-900 dark:text-white font-medium">{{ project.details.duration }}</span>
              </div>
              
              <div>
                <span class="text-sm text-gray-500 dark:text-gray-400 block">Statut</span>
                <span class="text-green-600 dark:text-green-400 font-medium">{{ project.details.status }}</span>
              </div>
              
              <div>
                <span class="text-sm text-gray-500 dark:text-gray-400 block">Catégorie</span>
                <span class="text-gray-900 dark:text-white font-medium">{{ project.details.category }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Gallerie d'images -->
      <div class="animate-fade-in">
        <h2 class="text-3xl font-bold text-gray-900 dark:text-white mb-8">Galerie du projet</h2>
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div 
            v-for="n in 3" 
            :key="n"
            class="bg-gradient-to-br from-primary-500/20 to-purple-600/20 rounded-2xl h-48 shadow-lg hover:shadow-xl transition-all duration-300 transform hover:scale-105"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()

// Données des projets (normalement depuis une API)
const projectsData = {
  1: {
    id: 1,
    title: 'Application E-commerce Moderne',
    fullDescription: 'Une plateforme e-commerce complète avec gestion des produits, panier d\'achat, et système de paiement sécurisé.',
    technologies: ['Vue.js', 'Node.js', 'MongoDB', 'Stripe', 'Express', 'JWT'],
    demoUrl: '#',
    githubUrl: '#',
    details: {
      objectives: 'Créer une solution e-commerce scalable et performante offrant une expérience utilisateur exceptionnelle sur tous les appareils.',
      features: [
        'Catalogue produits avec filtres avancés',
        'Panier persistant et sécurisé',
        'Intégration Stripe pour les paiements',
        'Interface d\'administration complète',
        'Recherche en temps réel',
        'Notifications par email'
      ],
      challenges: 'Gestion des transactions sécurisées, optimisation des performances pour de grands catalogues, et création d\'une interface intuitive pour les utilisateurs.',
      client: 'Startup E-commerce',
      duration: '4 mois',
      status: 'Live',
      category: 'E-commerce'
    }
  },
  2: {
    id: 2,
    title: 'Dashboard Analytics',
    fullDescription: 'Tableau de bord analytique en temps réel avec visualisations interactives et rapports personnalisables.',
    technologies: ['React', 'D3.js', 'Express', 'PostgreSQL', 'Socket.io'],
    demoUrl: '#',
    githubUrl: '#',
    details: {
      objectives: 'Développer une plateforme de visualisation de données permettant aux entreprises de suivre leurs KPIs en temps réel.',
      features: [
        'Graphiques interactifs et personnalisables',
        'Rapports automatiques programmables',
        'Alertes en temps réel',
        'Export des données en multiples formats',
        'Tableaux de bord partageables',
        'API REST complète'
      ],
      challenges: 'Traitement de grandes quantités de données en temps réel, création de visualisations complexes et maintenables, et optimisation des performances.',
      client: 'Entreprise SaaS',
      duration: '6 mois',
      status: 'Live',
      category: 'Analytics'
    }
  }
}

const project = computed(() => {
  return projectsData[route.params.id] || projectsData[1]
})
</script>