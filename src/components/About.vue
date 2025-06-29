<template>
  <section id="about" class="section-spacing bg-dark-900 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0">
      <div class="absolute top-1/4 right-0 w-96 h-96 bg-accent-500/10 rounded-full blur-3xl animate-pulse-slow"></div>
      <div class="absolute bottom-1/4 left-0 w-128 h-128 bg-primary-500/10 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 3s;"></div>
    </div>

    <div class="container-fluid relative z-10">
      <!-- Header -->
      <div class="text-center mb-24">
        <div class="inline-flex items-center space-x-3 px-6 py-3 bg-accent-500/10 border border-accent-400/30 rounded-full mb-8">
          <div class="w-2 h-2 bg-accent-400 rounded-full animate-pulse"></div>
          <span class="text-accent-400 font-mono text-sm tracking-wider">ABOUT US</span>
        </div>
        
        <h2 class="text-5xl lg:text-7xl font-black mb-8">
          <span class="block text-white">The Team Behind</span>
          <span class="block neon-text">The Future</span>
        </h2>
        
        <p class="text-xl text-white/70 max-w-4xl mx-auto leading-relaxed">
          We're not just developers—we're architects of tomorrow's digital infrastructure. 
          Our team combines deep technical expertise with visionary thinking to build systems that transform industries.
        </p>
      </div>

      <!-- Mission, Vision, Values -->
      <div class="grid lg:grid-cols-3 gap-12 mb-32">
        <div class="glass-card text-center group hover:scale-105 transition-all duration-500">
          <div class="w-20 h-20 bg-gradient-to-br from-accent-500 to-accent-600 rounded-3xl mx-auto mb-8 flex items-center justify-center transform group-hover:rotate-12 transition-transform duration-500">
            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 20 20">
              <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/>
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-white mb-6">Mission</h3>
          <p class="text-white/70 leading-relaxed">
            To democratize access to intelligent systems by building APIs and cloud infrastructure 
            that make advanced technology accessible to businesses of all sizes.
          </p>
        </div>

        <div class="glass-card text-center group hover:scale-105 transition-all duration-500">
          <div class="w-20 h-20 bg-gradient-to-br from-primary-500 to-primary-600 rounded-3xl mx-auto mb-8 flex items-center justify-center transform group-hover:rotate-12 transition-transform duration-500">
            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 20 20">
              <path d="M10 12a2 2 0 100-4 2 2 0 000 4z"/>
              <path fill-rule="evenodd" d="M.458 10C1.732 5.943 5.522 3 10 3s8.268 2.943 9.542 7c-1.274 4.057-5.064 7-9.542 7S1.732 14.057.458 10zM14 10a4 4 0 11-8 0 4 4 0 018 0z" clip-rule="evenodd"/>
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-white mb-6">Vision</h3>
          <p class="text-white/70 leading-relaxed">
            A world where every business operates with the intelligence and efficiency of tomorrow's 
            most advanced organizations, powered by our autonomous systems.
          </p>
        </div>

        <div class="glass-card text-center group hover:scale-105 transition-all duration-500">
          <div class="w-20 h-20 bg-gradient-to-br from-cyber-500 to-cyber-600 rounded-3xl mx-auto mb-8 flex items-center justify-center transform group-hover:rotate-12 transition-transform duration-500">
            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M6.267 3.455a3.066 3.066 0 001.745-.723 3.066 3.066 0 013.976 0 3.066 3.066 0 001.745.723 3.066 3.066 0 012.812 2.812c.051.643.304 1.254.723 1.745a3.066 3.066 0 010 3.976 3.066 3.066 0 00-.723 1.745 3.066 3.066 0 01-2.812 2.812 3.066 3.066 0 00-1.745.723 3.066 3.066 0 01-3.976 0 3.066 3.066 0 00-1.745-.723 3.066 3.066 0 01-2.812-2.812 3.066 3.066 0 00-.723-1.745 3.066 3.066 0 010-3.976 3.066 3.066 0 00.723-1.745 3.066 3.066 0 012.812-2.812zm7.44 5.252a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"/>
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-white mb-6">Values</h3>
          <p class="text-white/70 leading-relaxed">
            Innovation without compromise, security by design, and partnerships built on trust. 
            We believe technology should amplify human potential, not replace it.
          </p>
        </div>
      </div>

      <!-- Team Section -->
      <div class="text-center mb-16">
        <h3 class="text-4xl lg:text-5xl font-bold text-white mb-8">
          Meet the <span class="neon-text">Architects</span>
        </h3>
        <p class="text-xl text-white/70 max-w-3xl mx-auto">
          Our team of visionaries, engineers, and strategists who are reshaping the future of business technology.
        </p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <!-- Team Member 1 -->
        <div class="glass-card text-center group hover:scale-105 transition-all duration-500">
          <div class="relative mb-6">
            <div class="w-24 h-24 bg-gradient-to-br from-accent-500 to-primary-500 rounded-full mx-auto flex items-center justify-center transform group-hover:rotate-12 transition-transform duration-500">
              <span class="text-2xl font-bold text-white">JS</span>
            </div>
            <div class="absolute -inset-2 bg-gradient-to-r from-accent-500 to-primary-500 rounded-full blur opacity-0 group-hover:opacity-30 transition-opacity duration-500"></div>
          </div>
          <h4 class="text-xl font-bold text-white mb-2">James Smith</h4>
          <p class="text-accent-400 mb-3 font-mono text-sm">CHIEF_ARCHITECT</p>
          <p class="text-white/70 text-sm leading-relaxed">
            15+ years architecting distributed systems. Former Principal Engineer at major cloud providers.
          </p>
        </div>

        <!-- Team Member 2 -->
        <div class="glass-card text-center group hover:scale-105 transition-all duration-500">
          <div class="relative mb-6">
            <div class="w-24 h-24 bg-gradient-to-br from-primary-500 to-cyber-500 rounded-full mx-auto flex items-center justify-center transform group-hover:rotate-12 transition-transform duration-500">
              <span class="text-2xl font-bold text-white">MR</span>
            </div>
            <div class="absolute -inset-2 bg-gradient-to-r from-primary-500 to-cyber-500 rounded-full blur opacity-0 group-hover:opacity-30 transition-opacity duration-500"></div>
          </div>
          <h4 class="text-xl font-bold text-white mb-2">Maria Rodriguez</h4>
          <p class="text-primary-400 mb-3 font-mono text-sm">AI_LEAD</p>
          <p class="text-white/70 text-sm leading-relaxed">
            PhD in Machine Learning. Published researcher with 50+ papers in autonomous systems and neural networks.
          </p>
        </div>

        <!-- Team Member 3 -->
        <div class="glass-card text-center group hover:scale-105 transition-all duration-500">
          <div class="relative mb-6">
            <div class="w-24 h-24 bg-gradient-to-br from-cyber-500 to-accent-500 rounded-full mx-auto flex items-center justify-center transform group-hover:rotate-12 transition-transform duration-500">
              <span class="text-2xl font-bold text-white">DK</span>
            </div>
            <div class="absolute -inset-2 bg-gradient-to-r from-cyber-500 to-accent-500 rounded-full blur opacity-0 group-hover:opacity-30 transition-opacity duration-500"></div>
          </div>
          <h4 class="text-xl font-bold text-white mb-2">David Kim</h4>
          <p class="text-cyber-400 mb-3 font-mono text-sm">DEVOPS_MASTER</p>
          <p class="text-white/70 text-sm leading-relaxed">
            Kubernetes certified expert. Built CI/CD pipelines for Fortune 500 companies with zero-downtime deployments.
          </p>
        </div>

        <!-- Team Member 4 -->
        <div class="glass-card text-center group hover:scale-105 transition-all duration-500">
          <div class="relative mb-6">
            <div class="w-24 h-24 bg-gradient-to-br from-accent-600 to-primary-500 rounded-full mx-auto flex items-center justify-center transform group-hover:rotate-12 transition-transform duration-500">
              <span class="text-2xl font-bold text-white">SP</span>
            </div>
            <div class="absolute -inset-2 bg-gradient-to-r from-accent-600 to-primary-500 rounded-full blur opacity-0 group-hover:opacity-30 transition-opacity duration-500"></div>
          </div>
          <h4 class="text-xl font-bold text-white mb-2">Sarah Parker</h4>
          <p class="text-accent-400 mb-3 font-mono text-sm">API_SPECIALIST</p>
          <p class="text-white/70 text-sm leading-relaxed">
            Enterprise integration expert. Designed APIs serving billions of requests for global platforms.
          </p>
        </div>
      </div>

      <!-- Company Stats -->
      <div class="mt-32 grid md:grid-cols-4 gap-8">
        <div class="text-center">
          <div class="text-4xl lg:text-5xl font-bold neon-text mb-3">5+</div>
          <div class="text-white/60 font-mono text-sm tracking-wider">YEARS_EXPERIENCE</div>
        </div>
        <div class="text-center">
          <div class="text-4xl lg:text-5xl font-bold neon-text mb-3">100+</div>
          <div class="text-white/60 font-mono text-sm tracking-wider">SYSTEMS_DEPLOYED</div>
        </div>
        <div class="text-center">
          <div class="text-4xl lg:text-5xl font-bold neon-text mb-3">50+</div>
          <div class="text-white/60 font-mono text-sm tracking-wider">CLIENTS_SERVED</div>
        </div>
        <div class="text-center">
          <div class="text-4xl lg:text-5xl font-bold neon-text mb-3">24/7</div>
          <div class="text-white/60 font-mono text-sm tracking-wider">SUPPORT_AVAILABLE</div>
        </div>
      </div>
    </div>
  </section>
</template>