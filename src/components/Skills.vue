<template>
  <section id="skills" class="py-20 bg-gray-50 dark:bg-gray-900 transition-colors duration-300">
    <div class="container mx-auto px-4 sm:px-6">
      <h2 class="text-4xl font-bold text-center text-gray-900 dark:text-white mb-4 animate-fade-in">
        Mes Compétences
      </h2>
      
      <p class="text-center text-gray-600 dark:text-gray-300 mb-12 max-w-2xl mx-auto animate-fade-in">
        Technologies et outils que j'utilise pour créer des applications modernes
      </p>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="(category, index) in skills" 
          :key="category.name" 
          class="bg-white dark:bg-gray-800 rounded-2xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 transform hover:scale-105 animate-slide-up"
          :style="`animation-delay: ${index * 0.1}s`"
        >
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4 flex items-center">
            <span class="w-8 h-8 rounded-full bg-primary-500/10 flex items-center justify-center mr-3">
              <span class="text-primary-500 text-lg">{{ category.emoji }}</span>
            </span>
            {{ category.name }}
          </h3>
          
          <div class="space-y-4">
            <div 
              v-for="skill in category.items" 
              :key="skill.name" 
              class="flex items-center justify-between group"
            >
              <span class="text-gray-700 dark:text-gray-300 font-medium">{{ skill.name }}</span>
              <div class="flex items-center">
                <div class="w-24 bg-gray-200 dark:bg-gray-700 rounded-full h-2 mr-3">
                  <div 
                    class="bg-gradient-to-r from-primary-500 to-purple-600 h-2 rounded-full transition-all duration-1000 ease-out"
                    :style="{ width: skill.level + '%' }"
                  ></div>
                </div>
                <span class="text-sm text-gray-500 dark:text-gray-400 w-8">{{ skill.level }}%</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skills = [
  {
    name: 'Frontend',
    emoji: '⚡',
    items: [
      { name: 'Vue.js', level: 90 },
      { name: 'React', level: 85 },
      { name: 'JavaScript', level: 88 },
      { name: 'Tailwind CSS', level: 92 }
    ]
  },
  {
    name: 'Backend',
    emoji: '🔧',
    items: [
      { name: 'Python', level: 90 },
      { name: 'Django', level: 80 },
      { name: 'Node.js', level: 75 },
      { name: 'MySql', level: 75 },
      {name: 'PostgreSQL', level: 70},
      { name: 'API REST', level: 88 }
    ]
  },
  {
    name: 'Outils',
    emoji: '🚀',
    items: [
      { name: 'Git/GitHub', level: 90 },
      { name: 'Gitlab', level: 80 },
      { name: 'Figma', level: 60 },

    ]
  }
]
</script>