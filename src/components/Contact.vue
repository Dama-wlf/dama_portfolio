<template>
  <section id="contact" class="py-20 bg-gray-50 dark:bg-gray-900 transition-colors duration-300">
    <div class="container mx-auto px-4 sm:px-6">
      <h2 class="text-4xl font-bold text-center text-gray-900 dark:text-white mb-4 animate-fade-in">
        Contactez-moi
      </h2>
      
      <p class="text-center text-gray-600 dark:text-gray-300 mb-12 max-w-2xl mx-auto animate-fade-in">
        Discutons de votre prochain projet ensemble
      </p>
      
      <div class="grid lg:grid-cols-2 gap-12 max-w-6xl mx-auto">
        <!-- Informations de contact -->
        <div class="space-y-8 animate-slide-in-left">
          <div>
            <h3 class="text-2xl font-semibold text-gray-900 dark:text-white mb-6">
              Prenons contact
            </h3>
            <p class="text-gray-600 dark:text-gray-300 mb-8">
              N'hésitez pas à me contacter. Je serai ravi d'échanger avec vous.
            </p>
          </div>
          
          <div class="space-y-6">
            <div 
              v-for="contact in contactMethods" 
              :key="contact.type"
              class="flex items-center p-4 rounded-2xl bg-white dark:bg-gray-800 shadow-lg hover:shadow-xl transition-all duration-300 transform hover:scale-105"
            >
              <div class="w-12 h-12 rounded-full bg-primary-500/10 flex items-center justify-center mr-4">
                <component :is="contact.icon" class="w-6 h-6 text-primary-500" />
              </div>
              <div>
                <h4 class="font-semibold text-gray-900 dark:text-white">{{ contact.type }}</h4>
                <p class="text-gray-600 dark:text-gray-300">{{ contact.value }}</p>
              </div>
            </div>
          </div>
          
          <!-- Réseaux sociaux -->
          <div class="pt-6">
            <h4 class="font-semibold text-gray-900 dark:text-white mb-4">Suivez-moi</h4>
           <div class="flex space-x-4">
              <a 
                href="https://www.linkedin.com/in/anil-dama-tina-5b1056310/" 
                class="w-12 h-12 rounded-full bg-white dark:bg-gray-800 shadow-lg flex items-center justify-center hover:shadow-xl transition-all duration-300 transform hover:scale-110 hover:bg-blue-600 group"
                title="LinkedIn"
              >
                <svg class="w-6 h-6 text-blue-600 group-hover:text-white" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                </svg>
              </a>

              <a 
                href="https://facebook.com/anilschanone.dama" 
                class="w-12 h-12 rounded-full bg-white dark:bg-gray-800 shadow-lg flex items-center justify-center hover:shadow-xl transition-all duration-300 transform hover:scale-110 hover:bg-blue-500 group"
                title="Facebook"
              >
                <svg class="w-6 h-6 text-blue-500 group-hover:text-white" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                </svg>
              </a>

              <a 
                href="https://github.com/Dama-wlf" 
                class="w-12 h-12 rounded-full bg-white dark:bg-gray-800 shadow-lg flex items-center justify-center hover:shadow-xl transition-all duration-300 transform hover:scale-110 hover:bg-gray-800 group"
                title="GitHub"
              >
                <svg class="w-6 h-6 text-gray-800 dark:text-gray-300 group-hover:text-white" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>
            </div>
          </div>
        </div>
        
        <!-- Formulaire de contact -->
        <div class="animate-slide-in-right">
          <form @submit.prevent="handleSubmit" class="space-y-6">
            <div class="grid sm:grid-cols-2 gap-6">
              <div>
                <label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">
                  Nom complet *
                </label>
                <input
                  id="name"
                  v-model="form.name"
                  type="text"
                  required
                  class="w-full px-4 py-3 rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-gray-900 dark:text-white placeholder-gray-500 focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                  placeholder="Votre nom"
                >
              </div>
              
              <div>
                <label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">
                  Email *
                </label>
                <input
                  id="email"
                  v-model="form.email"
                  type="email"
                  required
                  class="w-full px-4 py-3 rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-gray-900 dark:text-white placeholder-gray-500 focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                  placeholder="votre@email.com"
                >
              </div>
            </div>
            
            <div>
              <label for="subject" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">
                Sujet *
              </label>
              <input
                id="subject"
                v-model="form.subject"
                type="text"
                required
                class="w-full px-4 py-3 rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-gray-900 dark:text-white placeholder-gray-500 focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                placeholder="Sujet de votre message"
              >
            </div>
            
            <div>
              <label for="message" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">
                Message *
              </label>
              <textarea
                id="message"
                v-model="form.message"
                rows="6"
                required
                class="w-full px-4 py-3 rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-gray-900 dark:text-white placeholder-gray-500 focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300 resize-none"
                placeholder="Décrivez votre projet..."
              ></textarea>
            </div>
            
            <div v-if="statusMessage" :class="statusClass" class="p-4 rounded-lg">
              {{ statusMessage }}
            </div>
            
            <button
              type="submit"
              :disabled="isSubmitting"
              class="w-full bg-primary-500 text-white py-4 px-8 rounded-xl font-semibold hover:bg-primary-600 transition-all duration-300 transform hover:scale-105 shadow-lg hover:shadow-xl disabled:opacity-50 disabled:cursor-not-allowed flex items-center justify-center"
            >
              <span v-if="!isSubmitting">Envoyer le message</span>
              <span v-else class="flex items-center">
                <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                  <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                  <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                </svg>
                Envoi en cours...
              </span>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import emailjs from 'emailjs-com'
import { EnvelopeIcon, PhoneIcon, MapPinIcon } from '@heroicons/vue/24/solid'

const statusMessage = ref('')
const statusClass = ref('')
const isSubmitting = ref(false)

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const contactMethods = [
  { type: 'Email', value: 'damaanil1504@gmail.com', icon: EnvelopeIcon },
  { type: 'Téléphone', value: '+261 32 53 948 38 / +261 34 58 850 81', icon: PhoneIcon },
  { type: 'Localisation', value: 'Antsirabe, Madagascar', icon: MapPinIcon },
]
const EMAILJS_CONFIG = {
  SERVICE_ID: 'service_clo0us2',  
  TEMPLATE_ID: 'template_u089mi2',
  USER_ID: 'fFX9R5TUF_pP-75Vz' 
}


const handleSubmit = async () => {
  isSubmitting.value = true
  statusMessage.value = ''
  
  try {
    // Envoi via EmailJS
    const result = await emailjs.send(
      EMAILJS_CONFIG.SERVICE_ID,
      EMAILJS_CONFIG.TEMPLATE_ID,
      {
        from_name: form.value.name,
        from_email: form.value.email,
        subject: form.value.subject,
        message: form.value.message,
        to_email: 'damaanil1504@gmail.com' 
      },
      EMAILJS_CONFIG.USER_ID
    )
    
    if (result.text === 'OK') {
      statusMessage.value = '✅ Message envoyé avec succès ! Je vous répondrai dans les plus brefs délais.'
      statusClass.value = 'bg-green-100 text-green-700 border border-green-200'
      
      form.value = { name: '', email: '', subject: '', message: '' }
    }
  } catch (error) {
    console.error('Erreur envoi email:', error)
    statusMessage.value = 'Une erreur est survenue. Veuillez réessayer ou me contacter directement par email.'
    statusClass.value = 'bg-red-100 text-red-700 border border-red-200'
  } finally {
    isSubmitting.value = false
    
    setTimeout(() => {
      statusMessage.value = ''
    }, 5000)
  }
}
</script>