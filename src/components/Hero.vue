<script setup lang="ts">
const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
  <section class="relative min-h-screen flex items-center overflow-hidden bg-dark-900">
    <!-- Animated Background -->
    <div class="absolute inset-0">
      <div class="absolute inset-0 grid-pattern opacity-20"></div>
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-accent-500/10 rounded-full blur-3xl animate-pulse-slow"></div>
      <div class="absolute bottom-1/4 right-1/4 w-128 h-128 bg-primary-500/10 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 2s;"></div>
      <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-144 h-144 bg-cyber-500/5 rounded-full blur-3xl animate-spin-slow"></div>
    </div>

    <div class="container-fluid relative z-10">
      <div class="grid lg:grid-cols-12 gap-16 items-center min-h-screen py-32">
        <!-- Content -->
        <div class="lg:col-span-7 space-y-12">
          <div class="space-y-8">
            <div class="inline-flex items-center space-x-3 px-6 py-3 bg-accent-500/10 border border-accent-400/30 rounded-full">
              <div class="w-2 h-2 bg-accent-400 rounded-full animate-pulse"></div>
              <span class="text-accent-400 font-mono text-sm tracking-wider">NEXT-GEN SYSTEMS</span>
            </div>
            
            <h1 class="text-6xl lg:text-8xl font-black leading-none">
              <span class="block text-white">Build</span>
              <span class="block neon-text text-shadow-glow">Intelligent</span>
              <span class="block text-white">Systems</span>
            </h1>
            
            <div class="max-w-2xl">
              <p class="text-xl lg:text-2xl text-white/70 leading-relaxed font-light">
                We architect <span class="text-accent-400 font-semibold">APIs</span> and deploy 
                <span class="text-primary-400 font-semibold">cloud-native intelligent systems</span> 
                that transform businesses into autonomous, data-driven organizations.
              </p>
            </div>
          </div>

          <div class="flex flex-col sm:flex-row gap-6">
            <button @click="scrollToSection('contact')" class="btn-cyber group">
              <span class="relative z-10 flex items-center space-x-3">
                <span>Initialize Project</span>
                <svg class="w-5 h-5 transform group-hover:translate-x-1 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
                </svg>
              </span>
            </button>
            <button @click="scrollToSection('services')" class="btn-ghost group">
              <span class="flex items-center space-x-3">
                <span>Explore Tech Stack</span>
                <svg class="w-5 h-5 transform group-hover:rotate-90 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"/>
                </svg>
              </span>
            </button>
          </div>

          <!-- Stats -->
          <div class="grid grid-cols-3 gap-8 pt-12 border-t border-white/10">
            <div class="text-center lg:text-left">
              <div class="text-3xl lg:text-4xl font-bold neon-text">99.9%</div>
              <div class="text-white/60 font-mono text-sm">UPTIME</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="text-3xl lg:text-4xl font-bold neon-text">50+</div>
              <div class="text-white/60 font-mono text-sm">SYSTEMS</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="text-3xl lg:text-4xl font-bold neon-text">24/7</div>
              <div class="text-white/60 font-mono text-sm">SUPPORT</div>
            </div>
          </div>
        </div>

        <!-- Visual Element -->
        <div class="lg:col-span-5 relative">
          <div class="relative">
            <!-- Central Hub -->
            <div class="relative mx-auto w-80 h-80 lg:w-96 lg:h-96">
              <!-- Core -->
              <div class="absolute inset-1/2 transform -translate-x-1/2 -translate-y-1/2 w-24 h-24 bg-gradient-to-br from-accent-500 to-primary-500 rounded-full animate-pulse-slow">
                <div class="absolute inset-2 bg-dark-900 rounded-full flex items-center justify-center">
                  <div class="w-8 h-8 bg-gradient-to-br from-accent-400 to-primary-400 rounded-full animate-spin-slow"></div>
                </div>
              </div>

              <!-- Orbiting Elements -->
              <div class="absolute inset-0 animate-spin-slow">
                <div class="absolute top-0 left-1/2 transform -translate-x-1/2 -translate-y-1/2 glass-card w-20 h-20 flex items-center justify-center">
                  <svg class="w-8 h-8 text-accent-400" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"/>
                  </svg>
                </div>
                
                <div class="absolute top-1/2 right-0 transform translate-x-1/2 -translate-y-1/2 glass-card w-20 h-20 flex items-center justify-center">
                  <svg class="w-8 h-8 text-primary-400" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/>
                  </svg>
                </div>
                
                <div class="absolute bottom-0 left-1/2 transform -translate-x-1/2 translate-y-1/2 glass-card w-20 h-20 flex items-center justify-center">
                  <svg class="w-8 h-8 text-cyber-400" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M3 3a1 1 0 000 2v8a2 2 0 002 2h2.586l-1.293 1.293a1 1 0 101.414 1.414L10 15.414l2.293 2.293a1 1 0 001.414-1.414L12.414 15H15a2 2 0 002-2V5a1 1 0 100-2H3z"/>
                  </svg>
                </div>
                
                <div class="absolute top-1/2 left-0 transform -translate-x-1/2 -translate-y-1/2 glass-card w-20 h-20 flex items-center justify-center">
                  <svg class="w-8 h-8 text-accent-400" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M6 2a1 1 0 00-1 1v1H4a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V6a2 2 0 00-2-2h-1V3a1 1 0 10-2 0v1H7V3a1 1 0 00-1-1zm0 5a1 1 0 000 2h8a1 1 0 100-2H6z" clip-rule="evenodd"/>
                  </svg>
                </div>
              </div>

              <!-- Connection Lines -->
              <div class="absolute inset-0">
                <svg class="w-full h-full" viewBox="0 0 400 400">
                  <defs>
                    <linearGradient id="line-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
                      <stop offset="0%" style="stop-color:#d946ef;stop-opacity:0.6" />
                      <stop offset="100%" style="stop-color:#0ea5e9;stop-opacity:0.6" />
                    </linearGradient>
                  </defs>
                  <circle cx="200" cy="200" r="150" fill="none" stroke="url(#line-gradient)" stroke-width="2" stroke-dasharray="10,5" opacity="0.5">
                    <animateTransform attributeName="transform" type="rotate" values="0 200 200;360 200 200" dur="20s" repeatCount="indefinite"/>
                  </circle>
                  <circle cx="200" cy="200" r="100" fill="none" stroke="url(#line-gradient)" stroke-width="1" stroke-dasharray="5,3" opacity="0.3">
                    <animateTransform attributeName="transform" type="rotate" values="360 200 200;0 200 200" dur="15s" repeatCount="indefinite"/>
                  </circle>
                </svg>
              </div>
            </div>

            <!-- Floating Data Points -->
            <div class="absolute -top-12 -right-12 glass-card p-4 floating-element">
              <div class="text-accent-400 font-mono text-sm">API_CALLS</div>
              <div class="text-white font-bold text-xl">1.2M/day</div>
            </div>
            
            <div class="absolute -bottom-12 -left-12 glass-card p-4 floating-element" style="animation-delay: 2s;">
              <div class="text-primary-400 font-mono text-sm">LATENCY</div>
              <div class="text-white font-bold text-xl">&lt;50ms</div>
            </div>
            
            <div class="absolute top-1/2 -right-20 glass-card p-4 floating-element" style="animation-delay: 4s;">
              <div class="text-cyber-400 font-mono text-sm">ACCURACY</div>
              <div class="text-white font-bold text-xl">99.8%</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-12 left-1/2 transform -translate-x-1/2">
      <div class="flex flex-col items-center space-y-4 animate-bounce-slow">
        <div class="text-white/60 font-mono text-xs tracking-wider">SCROLL</div>
        <div class="w-px h-12 bg-gradient-to-b from-accent-400 to-transparent"></div>
      </div>
    </div>
  </section>
</template>