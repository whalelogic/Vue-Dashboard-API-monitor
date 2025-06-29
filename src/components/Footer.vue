<script setup lang="ts">
const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<template>
  <footer class="bg-dark-900 border-t border-white/10 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0">
      <div class="absolute bottom-0 left-0 w-96 h-96 bg-accent-500/5 rounded-full blur-3xl"></div>
      <div class="absolute top-0 right-0 w-128 h-128 bg-primary-500/5 rounded-full blur-3xl"></div>
    </div>

    <div class="container-fluid relative z-10">
      <!-- Main Footer Content -->
      <div class="py-20 grid md:grid-cols-2 lg:grid-cols-4 gap-12">
        <!-- Company Info -->
        <div class="lg:col-span-2 space-y-8">
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
          
          <p class="text-white/70 max-w-md leading-relaxed">
            Architecting the intelligent systems that power tomorrow's businesses. 
            Your trusted partner for next-generation cloud infrastructure and AI solutions.
          </p>
          
          <div class="flex space-x-4">
            <a href="#" class="w-12 h-12 glass-card flex items-center justify-center hover:bg-accent-500/20 hover:border-accent-400/40 transition-all duration-300 group">
              <svg class="w-5 h-5 text-white/70 group-hover:text-accent-400 transition-colors duration-300" fill="currentColor" viewBox="0 0 24 24">
                <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
              </svg>
            </a>
            <a href="#" class="w-12 h-12 glass-card flex items-center justify-center hover:bg-primary-500/20 hover:border-primary-400/40 transition-all duration-300 group">
              <svg class="w-5 h-5 text-white/70 group-hover:text-primary-400 transition-colors duration-300" fill="currentColor" viewBox="0 0 24 24">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
            </a>
            <a href="#" class="w-12 h-12 glass-card flex items-center justify-center hover:bg-cyber-500/20 hover:border-cyber-400/40 transition-all duration-300 group">
              <svg class="w-5 h-5 text-white/70 group-hover:text-cyber-400 transition-colors duration-300" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
            </a>
          </div>
        </div>

        <!-- Quick Links -->
        <div>
          <h3 class="text-lg font-bold text-white mb-8">Navigation</h3>
          <ul class="space-y-4">
            <li>
              <button @click="scrollToSection('services')" class="text-white/70 hover:text-accent-400 transition-colors duration-300 font-mono text-sm">
                SERVICES
              </button>
            </li>
            <li>
              <button @click="scrollToSection('features')" class="text-white/70 hover:text-primary-400 transition-colors duration-300 font-mono text-sm">
                TECH_STACK
              </button>
            </li>
            <li>
              <button @click="scrollToSection('about')" class="text-white/70 hover:text-cyber-400 transition-colors duration-300 font-mono text-sm">
                ABOUT_TEAM
              </button>
            </li>
            <li>
              <button @click="scrollToSection('contact')" class="text-white/70 hover:text-accent-400 transition-colors duration-300 font-mono text-sm">
                CONTACT
              </button>
            </li>
          </ul>
        </div>

        <!-- Services -->
        <div>
          <h3 class="text-lg font-bold text-white mb-8">Core Services</h3>
          <ul class="space-y-4">
            <li>
              <a href="#" class="text-white/70 hover:text-accent-400 transition-colors duration-300 font-mono text-sm">
                API_ARCHITECTURE
              </a>
            </li>
            <li>
              <a href="#" class="text-white/70 hover:text-primary-400 transition-colors duration-300 font-mono text-sm">
                AI_SYSTEMS
              </a>
            </li>
            <li>
              <a href="#" class="text-white/70 hover:text-cyber-400 transition-colors duration-300 font-mono text-sm">
                CLOUD_OPS
              </a>
            </li>
            <li>
              <a href="#" class="text-white/70 hover:text-accent-400 transition-colors duration-300 font-mono text-sm">
                INTEGRATION
              </a>
            </li>
            <li>
              <a href="#" class="text-white/70 hover:text-primary-400 transition-colors duration-300 font-mono text-sm">
                CONSULTING
              </a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Bottom Footer -->
      <div class="border-t border-white/10 py-8">
        <div class="flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
          <div class="text-white/50 text-sm font-mono">
            © 2025 WHALER_SYSTEMS. ALL_RIGHTS_RESERVED.
          </div>
          <div class="flex space-x-8 text-sm">
            <a href="#" class="text-white/50 hover:text-accent-400 transition-colors duration-300 font-mono">
              PRIVACY_POLICY
            </a>
            <a href="#" class="text-white/50 hover:text-primary-400 transition-colors duration-300 font-mono">
              TERMS_OF_SERVICE
            </a>
            <a href="#" class="text-white/50 hover:text-cyber-400 transition-colors duration-300 font-mono">
              SECURITY_POLICY
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Back to Top Button -->
    <button
      @click="scrollToTop"
      class="fixed bottom-8 right-8 w-14 h-14 glass-card flex items-center justify-center hover:bg-accent-500/20 hover:border-accent-400/40 transition-all duration-300 transform hover:scale-110 z-50 group"
    >
      <svg class="w-6 h-6 text-white/70 group-hover:text-accent-400 transition-colors duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18"/>
      </svg>
    </button>
  </footer>
</template>