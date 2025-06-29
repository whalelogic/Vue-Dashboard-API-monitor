<template>
  <section id="features" class="section-spacing bg-dark-800 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0 holographic opacity-30"></div>
    <div class="absolute inset-0 cyber-grid opacity-10"></div>

    <div class="container-fluid relative z-10">
      <div class="grid lg:grid-cols-2 gap-20 items-center">
        <!-- Content -->
        <div class="space-y-12">
          <div>
            <div class="inline-flex items-center space-x-3 px-6 py-3 bg-cyber-500/10 border border-cyber-400/30 rounded-full mb-8">
              <div class="w-2 h-2 bg-cyber-400 rounded-full animate-pulse"></div>
              <span class="text-cyber-400 font-mono text-sm tracking-wider">TECH STACK</span>
            </div>
            
            <h2 class="text-5xl lg:text-6xl font-black mb-8">
              <span class="block text-white">Why Choose</span>
              <span class="block neon-text">Our Stack</span>
            </h2>
            
            <p class="text-xl text-white/70 leading-relaxed mb-12">
              We leverage cutting-edge technologies and proven methodologies to build systems that don't just work—they evolve.
            </p>
          </div>

          <!-- Features List -->
          <div class="space-y-8">
            <div class="flex items-start space-x-6 group">
              <div class="w-14 h-14 bg-gradient-to-br from-accent-500 to-accent-600 rounded-2xl flex items-center justify-center flex-shrink-0 transform group-hover:scale-110 transition-transform duration-300">
                <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M11.3 1.046A1 1 0 0112 2v5h4a1 1 0 01.82 1.573l-7 10A1 1 0 018 18v-5H4a1 1 0 01-.82-1.573l7-10a1 1 0 011.12-.38z" clip-rule="evenodd"/>
                </svg>
              </div>
              <div>
                <h3 class="text-2xl font-bold text-white mb-3">Lightning Performance</h3>
                <p class="text-white/70 leading-relaxed">Sub-50ms response times with intelligent caching, edge computing, and optimized data structures that scale infinitely.</p>
              </div>
            </div>

            <div class="flex items-start space-x-6 group">
              <div class="w-14 h-14 bg-gradient-to-br from-primary-500 to-primary-600 rounded-2xl flex items-center justify-center flex-shrink-0 transform group-hover:scale-110 transition-transform duration-300">
                <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M2.166 4.999A11.954 11.954 0 0010 1.944 11.954 11.954 0 0017.834 5c.11.65.166 1.32.166 2.001 0 5.225-3.34 9.67-8 11.317C5.34 16.67 2 12.225 2 7c0-.682.057-1.35.166-2.001zm11.541 3.708a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"/>
                </svg>
              </div>
              <div>
                <h3 class="text-2xl font-bold text-white mb-3">Zero-Trust Security</h3>
                <p class="text-white/70 leading-relaxed">Military-grade encryption, multi-factor authentication, and continuous security monitoring with automated threat response.</p>
              </div>
            </div>

            <div class="flex items-start space-x-6 group">
              <div class="w-14 h-14 bg-gradient-to-br from-cyber-500 to-cyber-600 rounded-2xl flex items-center justify-center flex-shrink-0 transform group-hover:scale-110 transition-transform duration-300">
                <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"/>
                </svg>
              </div>
              <div>
                <h3 class="text-2xl font-bold text-white mb-3">Infinite Scalability</h3>
                <p class="text-white/70 leading-relaxed">Auto-scaling architecture that grows from startup to enterprise without performance degradation or downtime.</p>
              </div>
            </div>

            <div class="flex items-start space-x-6 group">
              <div class="w-14 h-14 bg-gradient-to-br from-accent-600 to-primary-500 rounded-2xl flex items-center justify-center flex-shrink-0 transform group-hover:scale-110 transition-transform duration-300">
                <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/>
                </svg>
              </div>
              <div>
                <h3 class="text-2xl font-bold text-white mb-3">AI-Powered Monitoring</h3>
                <p class="text-white/70 leading-relaxed">Predictive analytics, anomaly detection, and self-healing systems that prevent issues before they occur.</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Tech Visualization -->
        <div class="relative">
          <div class="relative mx-auto max-w-lg">
            <!-- Central Node -->
            <div class="relative">
              <div class="w-32 h-32 bg-gradient-to-br from-accent-500 via-primary-500 to-cyber-500 rounded-3xl mx-auto mb-12 flex items-center justify-center transform rotate-12 animate-pulse-slow">
                <div class="w-20 h-20 bg-dark-900 rounded-2xl flex items-center justify-center transform -rotate-12">
                  <div class="w-8 h-8 bg-gradient-to-br from-accent-400 to-primary-400 rounded-lg animate-spin-slow"></div>
                </div>
              </div>
              
              <!-- Floating Tech Cards -->
              <div class="absolute -top-8 -left-8 glass-card p-4 floating-element">
                <div class="w-12 h-12 bg-gradient-to-br from-accent-500 to-accent-600 rounded-xl flex items-center justify-center mb-3">
                  <svg class="w-6 h-6 text-white" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                  </svg>
                </div>
                <div class="text-accent-400 font-mono text-xs">KUBERNETES</div>
              </div>
              
              <div class="absolute -top-8 -right-8 glass-card p-4 floating-element" style="animation-delay: 1s;">
                <div class="w-12 h-12 bg-gradient-to-br from-primary-500 to-primary-600 rounded-xl flex items-center justify-center mb-3">
                  <svg class="w-6 h-6 text-white" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                  </svg>
                </div>
                <div class="text-primary-400 font-mono text-xs">TENSORFLOW</div>
              </div>
              
              <div class="absolute -bottom-8 -left-8 glass-card p-4 floating-element" style="animation-delay: 2s;">
                <div class="w-12 h-12 bg-gradient-to-br from-cyber-500 to-cyber-600 rounded-xl flex items-center justify-center mb-3">
                  <svg class="w-6 h-6 text-white" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/>
                  </svg>
                </div>
                <div class="text-cyber-400 font-mono text-xs">DOCKER</div>
              </div>
              
              <div class="absolute -bottom-8 -right-8 glass-card p-4 floating-element" style="animation-delay: 3s;">
                <div class="w-12 h-12 bg-gradient-to-br from-accent-600 to-primary-500 rounded-xl flex items-center justify-center mb-3">
                  <svg class="w-6 h-6 text-white" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm5 11h-4v4h-2v-4H7v-2h4V7h2v4h4v2z"/>
                  </svg>
                </div>
                <div class="text-accent-400 font-mono text-xs">GRAPHQL</div>
              </div>
            </div>

            <!-- Performance Metrics -->
            <div class="grid grid-cols-2 gap-6 mt-16">
              <div class="glass-card text-center p-6">
                <div class="text-3xl font-bold neon-text mb-2">99.99%</div>
                <div class="text-white/60 font-mono text-sm">UPTIME</div>
              </div>
              <div class="glass-card text-center p-6">
                <div class="text-3xl font-bold neon-text mb-2">&lt;50ms</div>
                <div class="text-white/60 font-mono text-sm">LATENCY</div>
              </div>
              <div class="glass-card text-center p-6">
                <div class="text-3xl font-bold neon-text mb-2">10K+</div>
                <div class="text-white/60 font-mono text-sm">RPS</div>
              </div>
              <div class="glass-card text-center p-6">
                <div class="text-3xl font-bold neon-text mb-2">∞</div>
                <div class="text-white/60 font-mono text-sm">SCALE</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>