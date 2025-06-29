<template>
  <section id="services" class="section-spacing bg-dark-900 relative overflow-hidden">
    <!-- Background Elements -->
    <div class="absolute inset-0">
      <div class="absolute top-0 right-0 w-96 h-96 bg-accent-500/5 rounded-full blur-3xl"></div>
      <div class="absolute bottom-0 left-0 w-128 h-128 bg-primary-500/5 rounded-full blur-3xl"></div>
    </div>

    <div class="container-fluid relative z-10">
      <!-- Header -->
      <div class="text-center mb-24">
        <div class="inline-flex items-center space-x-3 px-6 py-3 bg-primary-500/10 border border-primary-400/30 rounded-full mb-8">
          <div class="w-2 h-2 bg-primary-400 rounded-full animate-pulse"></div>
          <span class="text-primary-400 font-mono text-sm tracking-wider">CORE SERVICES</span>
        </div>
        
        <h2 class="text-5xl lg:text-7xl font-black mb-8">
          <span class="block text-white">What We</span>
          <span class="block neon-text">Engineer</span>
        </h2>
        
        <p class="text-xl text-white/70 max-w-3xl mx-auto leading-relaxed">
          From concept to deployment, we build the intelligent infrastructure that powers next-generation businesses.
        </p>
      </div>

      <!-- Services Grid -->
      <div class="grid lg:grid-cols-2 gap-12 mb-24">
        <!-- API Architecture -->
        <div class="glass-card cyber-border group hover:scale-105 transition-all duration-500">
          <div class="flex items-start space-x-6 mb-8">
            <div class="w-16 h-16 bg-gradient-to-br from-accent-500 to-accent-600 rounded-2xl flex items-center justify-center transform rotate-3 group-hover:rotate-6 transition-transform duration-500">
              <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 20 20">
                <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"/>
              </svg>
            </div>
            <div>
              <h3 class="text-2xl lg:text-3xl font-bold text-white mb-3">API Architecture</h3>
              <p class="text-white/70 leading-relaxed">
                Design and build scalable, secure APIs that serve as the backbone of modern applications. 
                From REST to GraphQL, we create interfaces that scale.
              </p>
            </div>
          </div>
          
          <div class="grid grid-cols-2 gap-4 mb-6">
            <div class="bg-white/5 rounded-xl p-4 border border-accent-400/20">
              <div class="text-accent-400 font-mono text-sm mb-1">PERFORMANCE</div>
              <div class="text-white font-bold">&lt;100ms</div>
            </div>
            <div class="bg-white/5 rounded-xl p-4 border border-accent-400/20">
              <div class="text-accent-400 font-mono text-sm mb-1">THROUGHPUT</div>
              <div class="text-white font-bold">10K+ RPS</div>
            </div>
          </div>
          
          <div class="flex flex-wrap gap-2">
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">REST</span>
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">GraphQL</span>
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">WebSocket</span>
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">gRPC</span>
          </div>
        </div>

        <!-- AI Systems -->
        <div class="glass-card cyber-border group hover:scale-105 transition-all duration-500">
          <div class="flex items-start space-x-6 mb-8">
            <div class="w-16 h-16 bg-gradient-to-br from-primary-500 to-primary-600 rounded-2xl flex items-center justify-center transform -rotate-3 group-hover:-rotate-6 transition-transform duration-500">
              <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/>
              </svg>
            </div>
            <div>
              <h3 class="text-2xl lg:text-3xl font-bold text-white mb-3">AI Systems</h3>
              <p class="text-white/70 leading-relaxed">
                Deploy intelligent systems that learn, adapt, and optimize. From machine learning pipelines 
                to autonomous decision-making platforms.
              </p>
            </div>
          </div>
          
          <div class="grid grid-cols-2 gap-4 mb-6">
            <div class="bg-white/5 rounded-xl p-4 border border-primary-400/20">
              <div class="text-primary-400 font-mono text-sm mb-1">ACCURACY</div>
              <div class="text-white font-bold">99.8%</div>
            </div>
            <div class="bg-white/5 rounded-xl p-4 border border-primary-400/20">
              <div class="text-primary-400 font-mono text-sm mb-1">MODELS</div>
              <div class="text-white font-bold">50+ Active</div>
            </div>
          </div>
          
          <div class="flex flex-wrap gap-2">
            <span class="px-3 py-1 bg-primary-500/20 text-primary-400 rounded-full text-sm font-mono">TensorFlow</span>
            <span class="px-3 py-1 bg-primary-500/20 text-primary-400 rounded-full text-sm font-mono">PyTorch</span>
            <span class="px-3 py-1 bg-primary-500/20 text-primary-400 rounded-full text-sm font-mono">MLOps</span>
            <span class="px-3 py-1 bg-primary-500/20 text-primary-400 rounded-full text-sm font-mono">AutoML</span>
          </div>
        </div>

        <!-- Cloud Operations -->
        <div class="glass-card cyber-border group hover:scale-105 transition-all duration-500">
          <div class="flex items-start space-x-6 mb-8">
            <div class="w-16 h-16 bg-gradient-to-br from-cyber-500 to-cyber-600 rounded-2xl flex items-center justify-center transform rotate-3 group-hover:rotate-6 transition-transform duration-500">
              <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 20 20">
                <path d="M3 3a1 1 0 000 2v8a2 2 0 002 2h2.586l-1.293 1.293a1 1 0 101.414 1.414L10 15.414l2.293 2.293a1 1 0 001.414-1.414L12.414 15H15a2 2 0 002-2V5a1 1 0 100-2H3z"/>
              </svg>
            </div>
            <div>
              <h3 class="text-2xl lg:text-3xl font-bold text-white mb-3">Cloud Operations</h3>
              <p class="text-white/70 leading-relaxed">
                Build and manage cloud infrastructure that scales automatically. From Kubernetes orchestration 
                to serverless architectures.
              </p>
            </div>
          </div>
          
          <div class="grid grid-cols-2 gap-4 mb-6">
            <div class="bg-white/5 rounded-xl p-4 border border-cyber-400/20">
              <div class="text-cyber-400 font-mono text-sm mb-1">UPTIME</div>
              <div class="text-white font-bold">99.99%</div>
            </div>
            <div class="bg-white/5 rounded-xl p-4 border border-cyber-400/20">
              <div class="text-cyber-400 font-mono text-sm mb-1">SCALING</div>
              <div class="text-white font-bold">Auto</div>
            </div>
          </div>
          
          <div class="flex flex-wrap gap-2">
            <span class="px-3 py-1 bg-cyber-500/20 text-cyber-400 rounded-full text-sm font-mono">Kubernetes</span>
            <span class="px-3 py-1 bg-cyber-500/20 text-cyber-400 rounded-full text-sm font-mono">Docker</span>
            <span class="px-3 py-1 bg-cyber-500/20 text-cyber-400 rounded-full text-sm font-mono">AWS</span>
            <span class="px-3 py-1 bg-cyber-500/20 text-cyber-400 rounded-full text-sm font-mono">Terraform</span>
          </div>
        </div>

        <!-- System Integration -->
        <div class="glass-card cyber-border group hover:scale-105 transition-all duration-500">
          <div class="flex items-start space-x-6 mb-8">
            <div class="w-16 h-16 bg-gradient-to-br from-accent-600 to-primary-500 rounded-2xl flex items-center justify-center transform -rotate-3 group-hover:-rotate-6 transition-transform duration-500">
              <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M6 2a1 1 0 00-1 1v1H4a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V6a2 2 0 00-2-2h-1V3a1 1 0 10-2 0v1H7V3a1 1 0 00-1-1zm0 5a1 1 0 000 2h8a1 1 0 100-2H6z" clip-rule="evenodd"/>
              </svg>
            </div>
            <div>
              <h3 class="text-2xl lg:text-3xl font-bold text-white mb-3">System Integration</h3>
              <p class="text-white/70 leading-relaxed">
                Connect disparate systems into unified workflows. Legacy modernization, 
                data pipelines, and seamless third-party integrations.
              </p>
            </div>
          </div>
          
          <div class="grid grid-cols-2 gap-4 mb-6">
            <div class="bg-white/5 rounded-xl p-4 border border-accent-400/20">
              <div class="text-accent-400 font-mono text-sm mb-1">SYSTEMS</div>
              <div class="text-white font-bold">100+ Connected</div>
            </div>
            <div class="bg-white/5 rounded-xl p-4 border border-accent-400/20">
              <div class="text-accent-400 font-mono text-sm mb-1">DATA FLOW</div>
              <div class="text-white font-bold">Real-time</div>
            </div>
          </div>
          
          <div class="flex flex-wrap gap-2">
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">Apache Kafka</span>
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">ETL</span>
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">Webhooks</span>
            <span class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-full text-sm font-mono">Microservices</span>
          </div>
        </div>
      </div>

      <!-- Process Flow -->
      <div class="text-center">
        <h3 class="text-3xl lg:text-4xl font-bold text-white mb-12">Our Process</h3>
        <div class="grid md:grid-cols-4 gap-8">
          <div class="relative">
            <div class="w-16 h-16 bg-gradient-to-br from-accent-500 to-primary-500 rounded-full mx-auto mb-6 flex items-center justify-center">
              <span class="text-white font-bold text-xl">01</span>
            </div>
            <h4 class="text-xl font-bold text-white mb-3">Analyze</h4>
            <p class="text-white/70">Deep dive into your current systems and requirements</p>
            <div class="hidden md:block absolute top-8 left-full w-full h-px bg-gradient-to-r from-accent-400 to-transparent"></div>
          </div>
          
          <div class="relative">
            <div class="w-16 h-16 bg-gradient-to-br from-primary-500 to-cyber-500 rounded-full mx-auto mb-6 flex items-center justify-center">
              <span class="text-white font-bold text-xl">02</span>
            </div>
            <h4 class="text-xl font-bold text-white mb-3">Design</h4>
            <p class="text-white/70">Architect scalable solutions tailored to your needs</p>
            <div class="hidden md:block absolute top-8 left-full w-full h-px bg-gradient-to-r from-primary-400 to-transparent"></div>
          </div>
          
          <div class="relative">
            <div class="w-16 h-16 bg-gradient-to-br from-cyber-500 to-accent-500 rounded-full mx-auto mb-6 flex items-center justify-center">
              <span class="text-white font-bold text-xl">03</span>
            </div>
            <h4 class="text-xl font-bold text-white mb-3">Build</h4>
            <p class="text-white/70">Develop and test with cutting-edge technologies</p>
            <div class="hidden md:block absolute top-8 left-full w-full h-px bg-gradient-to-r from-cyber-400 to-transparent"></div>
          </div>
          
          <div>
            <div class="w-16 h-16 bg-gradient-to-br from-accent-500 to-primary-500 rounded-full mx-auto mb-6 flex items-center justify-center">
              <span class="text-white font-bold text-xl">04</span>
            </div>
            <h4 class="text-xl font-bold text-white mb-3">Deploy</h4>
            <p class="text-white/70">Launch and monitor with 24/7 support</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>