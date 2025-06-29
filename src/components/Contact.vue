<script setup lang="ts">
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  company: '',
  service: '',
  message: ''
})

const isSubmitting = ref(false)
const isSubmitted = ref(false)

const handleSubmit = async () => {
  isSubmitting.value = true
  
  // Simulate form submission
  await new Promise(resolve => setTimeout(resolve, 2000))
  
  isSubmitting.value = false
  isSubmitted.value = true
  
  // Reset form after success message
  setTimeout(() => {
    isSubmitted.value = false
    form.value = {
      name: '',
      email: '',
      company: '',
      service: '',
      message: ''
    }
  }, 4000)
}
</script>

<template>
  <section id="contact" class="section-spacing bg-dark-900 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0">
      <div class="absolute top-0 right-1/4 w-96 h-96 bg-accent-500/10 rounded-full blur-3xl animate-pulse-slow"></div>
      <div class="absolute bottom-0 left-1/4 w-128 h-128 bg-primary-500/10 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 2s;"></div>
      <div class="grid-pattern opacity-5"></div>
    </div>

    <div class="container-fluid relative z-10">
      <!-- Header -->
      <div class="text-center mb-24">
        <div class="inline-flex items-center space-x-3 px-6 py-3 bg-cyber-500/10 border border-cyber-400/30 rounded-full mb-8">
          <div class="w-2 h-2 bg-cyber-400 rounded-full animate-pulse"></div>
          <span class="text-cyber-400 font-mono text-sm tracking-wider">INITIALIZE_PROJECT</span>
        </div>
        
        <h2 class="text-5xl lg:text-7xl font-black mb-8">
          <span class="block text-white">Ready to Build</span>
          <span class="block neon-text">The Future?</span>
        </h2>
        
        <p class="text-xl text-white/70 max-w-4xl mx-auto leading-relaxed">
          Let's architect intelligent systems that transform your business. 
          Our team is ready to turn your vision into reality.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-20">
        <!-- Contact Information -->
        <div class="space-y-12">
          <div>
            <h3 class="text-3xl font-bold text-white mb-8">Connect With Us</h3>
            
            <div class="space-y-8">
              <!-- Email -->
              <div class="flex items-start space-x-6 group">
                <div class="w-14 h-14 bg-gradient-to-br from-accent-500 to-accent-600 rounded-2xl flex items-center justify-center flex-shrink-0 transform group-hover:scale-110 transition-transform duration-300">
                  <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"/>
                    <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"/>
                  </svg>
                </div>
                <div>
                  <h4 class="text-xl font-bold text-white mb-2">Email</h4>
                  <p class="text-accent-400 font-mono">hello@whalersystems.com</p>
                  <p class="text-white/60 text-sm">Response within 2 hours</p>
                </div>
              </div>

              <!-- Phone -->
              <div class="flex items-start space-x-6 group">
                <div class="w-14 h-14 bg-gradient-to-br from-primary-500 to-primary-600 rounded-2xl flex items-center justify-center flex-shrink-0 transform group-hover:scale-110 transition-transform duration-300">
                  <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z"/>
                  </svg>
                </div>
                <div>
                  <h4 class="text-xl font-bold text-white mb-2">Direct Line</h4>
                  <p class="text-primary-400 font-mono">+1 (555) 123-4567</p>
                  <p class="text-white/60 text-sm">24/7 Emergency Support</p>
                </div>
              </div>

              <!-- Location -->
              <div class="flex items-start space-x-6 group">
                <div class="w-14 h-14 bg-gradient-to-br from-cyber-500 to-cyber-600 rounded-2xl flex items-center justify-center flex-shrink-0 transform group-hover:scale-110 transition-transform duration-300">
                  <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd"/>
                  </svg>
                </div>
                <div>
                  <h4 class="text-xl font-bold text-white mb-2">HQ</h4>
                  <p class="text-cyber-400 font-mono">San Francisco, CA</p>
                  <p class="text-white/60 text-sm">Global Remote Team</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Response Time -->
          <div class="glass-card p-8">
            <h4 class="text-xl font-bold text-white mb-6">Response Times</h4>
            <div class="space-y-4">
              <div class="flex justify-between items-center">
                <span class="text-white/70">Initial Response</span>
                <span class="text-accent-400 font-mono">&lt; 2 hours</span>
              </div>
              <div class="flex justify-between items-center">
                <span class="text-white/70">Project Proposal</span>
                <span class="text-primary-400 font-mono">&lt; 24 hours</span>
              </div>
              <div class="flex justify-between items-center">
                <span class="text-white/70">Emergency Support</span>
                <span class="text-cyber-400 font-mono">Immediate</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Contact Form -->
        <div class="glass-card p-8 lg:p-12">
          <form @submit.prevent="handleSubmit" class="space-y-8">
            <div class="grid md:grid-cols-2 gap-6">
              <div>
                <label for="name" class="block text-white font-semibold mb-3">
                  Name*
                </label>
                <input
                  type="text"
                  id="name"
                  v-model="form.name"
                  required
                  class="w-full px-6 py-4 bg-white/5 border border-white/20 rounded-2xl text-white placeholder-white/50 focus:border-accent-400 focus:bg-white/10 transition-all duration-300"
                  placeholder="Your full name"
                />
              </div>
              
              <div>
                <label for="email" class="block text-white font-semibold mb-3">
                  Email*
                </label>
                <input
                  type="email"
                  id="email"
                  v-model="form.email"
                  required
                  class="w-full px-6 py-4 bg-white/5 border border-white/20 rounded-2xl text-white placeholder-white/50 focus:border-accent-400 focus:bg-white/10 transition-all duration-300"
                  placeholder="your@email.com"
                />
              </div>
            </div>

            <div class="grid md:grid-cols-2 gap-6">
              <div>
                <label for="company" class="block text-white font-semibold mb-3">
                  Company
                </label>
                <input
                  type="text"
                  id="company"
                  v-model="form.company"
                  class="w-full px-6 py-4 bg-white/5 border border-white/20 rounded-2xl text-white placeholder-white/50 focus:border-accent-400 focus:bg-white/10 transition-all duration-300"
                  placeholder="Your company"
                />
              </div>
              
              <div>
                <label for="service" class="block text-white font-semibold mb-3">
                  Service Interest
                </label>
                <select
                  id="service"
                  v-model="form.service"
                  class="w-full px-6 py-4 bg-white/5 border border-white/20 rounded-2xl text-white focus:border-accent-400 focus:bg-white/10 transition-all duration-300"
                >
                  <option value="" class="bg-dark-900">Select a service</option>
                  <option value="api-architecture" class="bg-dark-900">API Architecture</option>
                  <option value="ai-systems" class="bg-dark-900">AI Systems</option>
                  <option value="cloud-operations" class="bg-dark-900">Cloud Operations</option>
                  <option value="system-integration" class="bg-dark-900">System Integration</option>
                  <option value="consulting" class="bg-dark-900">Consulting</option>
                </select>
              </div>
            </div>

            <div>
              <label for="message" class="block text-white font-semibold mb-3">
                Project Details*
              </label>
              <textarea
                id="message"
                v-model="form.message"
                required
                rows="6"
                class="w-full px-6 py-4 bg-white/5 border border-white/20 rounded-2xl text-white placeholder-white/50 focus:border-accent-400 focus:bg-white/10 transition-all duration-300 resize-none"
                placeholder="Tell us about your project, current challenges, and goals..."
              ></textarea>
            </div>

            <button
              type="submit"
              :disabled="isSubmitting || isSubmitted"
              :class="[
                'w-full py-6 px-8 font-bold rounded-2xl transition-all duration-500 transform relative overflow-hidden',
                isSubmitted 
                  ? 'bg-gradient-to-r from-cyber-500 to-cyber-600 text-white'
                  : isSubmitting
                    ? 'bg-white/10 text-white/50 cursor-not-allowed'
                    : 'bg-gradient-to-r from-accent-500 to-primary-500 text-white hover:scale-105 hover:shadow-2xl hover:shadow-accent-500/25'
              ]"
            >
              <span v-if="isSubmitting" class="flex items-center justify-center space-x-3">
                <div class="w-6 h-6 border-2 border-white/30 border-t-white rounded-full animate-spin"></div>
                <span>Initializing...</span>
              </span>
              <span v-else-if="isSubmitted" class="flex items-center justify-center space-x-3">
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/>
                </svg>
                <span>Message Sent Successfully!</span>
              </span>
              <span v-else class="flex items-center justify-center space-x-3">
                <span>Initialize Project</span>
                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
                </svg>
              </span>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>