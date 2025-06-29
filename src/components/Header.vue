<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 100
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
  isMobileMenuOpen.value = false
}
</script>

<template>
  <header 
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-500',
      isScrolled ? 'bg-dark-900/80 backdrop-blur-xl border-b border-accent-400/20' : 'bg-transparent'
    ]"
  >
    <nav class="container-fluid">
      <div class="flex items-center justify-between h-20 lg:h-24">
        <!-- Logo -->
        <div class="flex items-center space-x-4">
          <div class="relative">
            <div class="w-12 h-12 bg-gradient-to-br from-accent-500 to-primary-500 rounded-lg flex items-center justify-center transform rotate-45">
              <div class="w-6 h-6 bg-dark-900 rounded-sm transform -rotate-45 flex items-center justify-center">
                <div class="w-3 h-3 bg-gradient-to-br from-accent-400 to-primary-400 rounded-full animate-pulse"></div>
              </div>
            </div>
            <div class="absolute -inset-1 bg-gradient-to-r from-accent-500 to-primary-500 rounded-lg blur opacity-30 animate-pulse-slow"></div>
          </div>
          <div>
            <span class="text-2xl font-bold neon-text">Whaler</span>
            <div class="text-xs text-accent-400 font-mono tracking-wider">SYSTEMS</div>
          </div>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden lg:flex items-center space-x-12">
          <button 
            @click="scrollToSection('services')"
            class="relative text-white/80 hover:text-accent-400 font-medium transition-all duration-300 group"
          >
            Services
            <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-gradient-to-r from-accent-400 to-primary-400 transition-all duration-300 group-hover:w-full"></span>
          </button>
          <button 
            @click="scrollToSection('features')"
            class="relative text-white/80 hover:text-accent-400 font-medium transition-all duration-300 group"
          >
            Tech
            <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-gradient-to-r from-accent-400 to-primary-400 transition-all duration-300 group-hover:w-full"></span>
          </button>
          <button 
            @click="scrollToSection('about')"
            class="relative text-white/80 hover:text-accent-400 font-medium transition-all duration-300 group"
          >
            About
            <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-gradient-to-r from-accent-400 to-primary-400 transition-all duration-300 group-hover:w-full"></span>
          </button>
          <button 
            @click="scrollToSection('contact')"
            class="btn-cyber relative z-10"
          >
            <span class="relative z-10">Initialize Project</span>
          </button>
        </div>

        <!-- Mobile Menu Button -->
        <button 
          @click="isMobileMenuOpen = !isMobileMenuOpen"
          class="lg:hidden p-3 text-white hover:text-accent-400 transition-colors duration-300"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div 
        v-if="isMobileMenuOpen"
        class="lg:hidden absolute top-full left-0 right-0 bg-dark-900/95 backdrop-blur-xl border-b border-accent-400/20 p-6"
      >
        <div class="flex flex-col space-y-6">
          <button @click="scrollToSection('services')" class="text-white/80 hover:text-accent-400 font-medium text-left transition-colors duration-300">
            Services
          </button>
          <button @click="scrollToSection('features')" class="text-white/80 hover:text-accent-400 font-medium text-left transition-colors duration-300">
            Tech
          </button>
          <button @click="scrollToSection('about')" class="text-white/80 hover:text-accent-400 font-medium text-left transition-colors duration-300">
            About
          </button>
          <button @click="scrollToSection('contact')" class="btn-cyber w-full">
            <span class="relative z-10">Initialize Project</span>
          </button>
        </div>
      </div>
    </nav>
  </header>
</template>