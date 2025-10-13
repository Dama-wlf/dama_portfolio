<template>
  <section id="about" class="py-12 md:py-20 bg-white dark:bg-gray-800 transition-colors duration-300">
    <div class="container mx-auto px-4 sm:px-6">
      <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-900 dark:text-white mb-4 animate-fade-in">
        À propos de moi
      </h2>
      
      <div class="max-w-3xl mx-auto text-center mb-8 md:mb-12">
        <p class="text-lg md:text-xl text-gray-600 dark:text-gray-300 animate-fade-in">
          Passionné par le développement web et l'innovation technologique
        </p>
      </div>
      
      <div class="grid lg:grid-cols-2 gap-8 md:gap-12 items-start">
        <!-- Contenu personnel -->
        <div class="space-y-6 animate-slide-in-left">
          <h3 class="text-xl md:text-2xl lg:text-3xl font-semibold text-gray-900 dark:text-white">
            Créateur d'expériences digitales <span class="text-primary-600 dark:text-primary-400">exceptionnelles</span>
          </h3>
          
          <div class="space-y-4 text-gray-600 dark:text-gray-300 leading-relaxed text-sm md:text-base">
            <p>
              Développeur full-stack spécialisé dans la création 
              d'applications web performantes et évolutives.
            </p>
            
            <p>
              Je mets mon expertise au service de projets innovants, en alliant 
              <strong>créativité</strong> et <strong>excellence technique</strong> pour 
              deliver des solutions qui marquent les esprits.
            </p>
          </div>
          
          <!-- Informations personnelles - CORRIGÉ POUR MOBILE -->
          <div class="grid grid-cols-1 xs:grid-cols-2 gap-3 md:gap-4 pt-4">
            <div 
              v-for="info in personalInfo" 
              :key="info.label" 
              class="flex flex-col xs:flex-row xs:items-center p-3 rounded-lg bg-gray-50 dark:bg-gray-700/50 hover:bg-gray-100 dark:hover:bg-gray-700 transition-colors duration-300 min-h-[60px]"
            >
              <span class="font-semibold text-gray-900 dark:text-white mb-1 xs:mb-0 xs:mr-2 text-xs md:text-sm whitespace-nowrap">
                {{ info.label }}:
              </span>
              <span class="text-gray-600 dark:text-gray-300 text-xs md:text-sm break-words xs:break-normal">
                {{ info.value }}
              </span>
            </div>
          </div>
        </div>
        
        <!-- Formations et Études -->
        <div class="space-y-6 md:space-y-8 animate-slide-up">
          <div>
            <h3 class="text-xl md:text-2xl font-semibold text-gray-900 dark:text-white mb-4 md:mb-6 flex items-center">
              <span class="w-6 h-6 md:w-8 md:h-8 bg-primary-500 rounded-full flex items-center justify-center mr-2 md:mr-3 flex-shrink-0">
                <span class="text-white text-xs md:text-sm">🎓</span>
              </span>
              Mon Parcours Académique
            </h3>
            
            <div class="space-y-4 md:space-y-6">
              <div 
                v-for="(formation, index) in formations" 
                :key="formation.id"
                class="relative pl-6 md:pl-8 pb-4 md:pb-6 border-l-2 border-primary-500/30"
                :class="index === formations.length - 1 ? '' : 'border-l-2'"
              >
                <!-- Point de timeline -->
                <div class="absolute -left-1.5 md:-left-2 w-3 h-3 md:w-4 md:h-4 bg-primary-500 rounded-full border-2 md:border-4 border-white dark:border-gray-800 flex-shrink-0"></div>
                
                <div class="bg-gray-50 dark:bg-gray-700/50 rounded-xl p-3 md:p-4 hover:shadow-lg transition-all duration-300">
                  <div class="flex flex-col sm:flex-row sm:justify-between sm:items-start gap-2 mb-2">
                    <h4 class="font-semibold text-gray-900 dark:text-white text-base md:text-lg">
                      {{ formation.diplome }}
                    </h4>
                    <span class="bg-primary-500/10 text-primary-600 dark:text-primary-400 px-2 py-1 rounded-full text-xs font-medium whitespace-nowrap self-start">
                      {{ formation.annee }}
                    </span>
                  </div>
                  
                  <p class="text-primary-600 dark:text-primary-400 font-medium mb-2 text-sm md:text-base">
                    {{ formation.etablissement }}
                  </p>
                  
                  <p class="text-gray-600 dark:text-gray-300 text-xs md:text-sm mb-3 leading-relaxed">
                    {{ formation.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const personalInfo = [
  { label: 'Nom', value: 'TINA Anil Dama' },
  { label: 'Email', value: 'damaanil1504@gmail.com' },
  { label: 'Téléphone', value: '+261 32 53 948 38 / +261 34 58 850 81' },
  { label: 'Localisation', value: 'Antsirabe, Madagascar' },
]

const formations = [
  {
    id: 1,
    diplome: "Master en Génie Logiciel",
    etablissement: "Université Athénée Saint Joseph Antsirabe (A.S.J.A)",
    annee: "En cours (2024-2025)",
    description: "Spécialisation en architectures modernes et technologies émergentes du web.",
  },
  {
    id: 2,
    diplome: "Licence Informatique",
    etablissement: "Université Athénée Saint Joseph Antsirabe (A.S.J.A)",
    annee: "2022-2023",
    description: "Formation fondamentale en informatique avec orientation Développement d'Application Informatique (D.A.I)",
  },
  {
    id: 3,
    diplome: "Baccalauréat Série D",
    etablissement: "SE.VE.MA Ambanja",
    annee: "2018 - 2019",
    description: "Baccalaureat, option Scientifique",
  }
]
</script>

<style scoped>
/* Animation pour la timeline */
@keyframes slideInFromLeft {
  from {
    opacity: 0;
    transform: translateX(-20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.relative.pl-6, .relative.pl-8 {
  animation: slideInFromLeft 0.6s ease-out;
}

/* Breakpoint personnalisé pour très petits écrans */
@media (max-width: 475px) {
  .xs\:grid-cols-2 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
  
  .xs\:flex-row {
    flex-direction: row;
  }
  
  .xs\:mb-0 {
    margin-bottom: 0;
  }
  
  .xs\:mr-2 {
    margin-right: 0.5rem;
  }
  
  .xs\:break-normal {
    word-break: normal;
    overflow-wrap: normal;
  }
}
</style>