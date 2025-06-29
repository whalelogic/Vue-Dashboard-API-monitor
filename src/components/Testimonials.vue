<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlide = ref(0)
let interval: number | null = null

const testimonials = [
  {
    name: "Alex Chen",
    position: "CTO",
    company: "TechFlow Solutions",
    content: "Whaler Systems didn't just build our API—they architected our entire digital transformation. Their intelligent systems approach took us from 10K to 10M requests per day with zero downtime. Absolutely revolutionary.",
    rating: 5,
    metric: "1000% Scale Increase"
  },
  {
    name: "Sarah Johnson",
    position: "VP Engineering",
    company: "DataCorp",
    content: "The AI-powered automation they deployed reduced our operational overhead by 70% while improving accuracy to 99.8%. Their team doesn't just code—they think like business strategists.",
    rating: 5,
    metric: "70% Cost Reduction"
  },
  {
    name: "Michael Torres",
    position: "Founder",
    company: "InnovateLab",
    content: "Working with Whaler Systems was like having a crystal ball for our tech stack. They predicted our scaling needs and built systems that grew seamlessly with our 500% user growth.",
    rating: 5,
    metric: "500% User Growth"
  },
  {
    name: "Lisa Wang",
    position: "Head of Technology",
    company: "FinanceNext",
    content: "Their cloud operations expertise is unmatched. The intelligent monitoring and self-healing systems they implemented have given us 99.99% uptime for 18 months straight.",
    rating: 5,
    metric: "99.99% Uptime"
  }
]

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % testimonials.length
}

const prevSlide = () => {
  currentSlide.value = currentSlide.value === 0 ? testimonials.length - 1 : currentSlide.value - 1
}

const goToSlide = (index: number) => {
  currentSlide.value = index
}

onMounted(() => {
  interval = setInterval(nextSlide, 6000)
})

onUnmounted(() => {
  if (interval) {
    clearInterval(interval)
  }
})
</script>

<template>
  <section class="section-spacing bg-dark-800 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0 holographic opacity-20"></div>
    <div class="absolute top-0 left-1/4 w-96 h-96 bg-primary-500/10 rounded-full blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 right-1/4 w-128 h-128 bg-accent-500/10 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 4s;"></div>

    <div class="container-fluid relative z-10">
      <!-- Header -->
      <div class="text-center mb-24">
        <div class="inline-flex items-center space-x-3 px-6 py-3 bg-primary-500/10 border border-primary-400/30 rounded-full mb-8">
          <div class="w-2 h-2 bg-primary-400 rounded-full animate-pulse"></div>
          <span class="text-primary-400 font-mono text-sm tracking-wider">CLIENT_TESTIMONIALS</span>
        </div>
        
        <h2 class="text-5xl lg:text-7xl font-black mb-8">
          <span class="block text-white">Success</span>
          <span class="block neon-text">Stories</span>
        </h2>
        
        <p class="text-xl text-white/70 max-w-3xl mx-auto">
          Real results from real companies who trusted us to transform their digital infrastructure.
        </p>
      </div>

      <!-- Testimonials Carousel -->
      <div class="relative max-w-6xl mx-auto">
        <div class="glass-card p-12 lg:p-16 relative overflow-hidden">
          <!-- Quote Background -->
          <div class="absolute top-8 right-8 w-24 h-24 opacity-10">
            <svg fill="currentColor" viewBox="0 0 100 100" class="w-full h-full text-accent-400">
              <path d="M30,50c0-11.046,8.954-20,20-20s20,8.954,20,20s-8.954,20-20,20S30,61.046,30,50z M50,65c8.271,0,15-6.729,15-15s-6.729-15-15-15s-15,6.729-15,15S41.729,65,50,65z"/>
            </svg>
          </div>

          <div class="relative">
            <!-- Testimonial Content -->
            <div class="transition-all duration-700 ease-in-out">
              <div class="mb-8">
                <p class="text-2xl lg:text-3xl text-white leading-relaxed font-light">
                  "{{ testimonials[currentSlide].content }}"
                </p>
              </div>

              <!-- Metric Highlight -->
              <div class="inline-flex items-center space-x-3 px-6 py-3 bg-accent-500/10 border border-accent-400/30 rounded-full mb-8">
                <div class="w-2 h-2 bg-accent-400 rounded-full animate-pulse"></div>
                <span class="text-accent-400 font-mono text-sm tracking-wider">{{ testimonials[currentSlide].metric }}</span>
              </div>

              <!-- Rating Stars -->
              <div class="flex justify-center mb-8">
                <div class="flex space-x-1">
                  <svg 
                    v-for="i in 5" 
                    :key="i"
                    class="w-6 h-6 text-accent-400" 
                    fill="currentColor" 
                    viewBox="0 0 20 20"
                  >
                    <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/>
                  </svg>
                </div>
              </div>

              <!-- Author -->
              <div class="text-center">
                <h4 class="text-2xl font-bold text-white mb-2">{{ testimonials[currentSlide].name }}</h4>
                <p class="text-white/70 mb-1">{{ testimonials[currentSlide].position }}</p>
                <p class="text-accent-400 font-mono text-sm tracking-wider">{{ testimonials[currentSlide].company }}</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Navigation Arrows -->
        <button 
          @click="prevSlide"
          class="absolute left-4 top-1/2 transform -translate-y-1/2 w-14 h-14 glass-card flex items-center justify-center hover:bg-white/20 transition-all duration-300 group"
        >
          <svg class="w-6 h-6 text-white group-hover:text-accent-400 transition-colors duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"/>
          </svg>
        </button>
        
        <button 
          @click="nextSlide"
          class="absolute right-4 top-1/2 transform -translate-y-1/2 w-14 h-14 glass-card flex items-center justify-center hover:bg-white/20 transition-all duration-300 group"
        >
          <svg class="w-6 h-6 text-white group-hover:text-accent-400 transition-colors duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
          </svg>
        </button>

        <!-- Dots Indicator -->
        <div class="flex justify-center mt-12 space-x-3">
          <button
            v-for="(testimonial, index) in testimonials"
            :key="index"
            @click="goToSlide(index)"
            :class="[
              'w-4 h-4 rounded-full transition-all duration-300',
              currentSlide === index 
                ? 'bg-accent-400 scale-125' 
                : 'bg-white/30 hover:bg-white/50'
            ]"
          />
        </div>
      </div>

      <!-- Client Logos -->
      <div class="mt-24 text-center">
        <h3 class="text-2xl font-bold text-white mb-12">Trusted by Industry Leaders</h3>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8 opacity-60">
          <div class="glass-card p-6 flex items-center justify-center">
            <div class="text-white font-bold text-xl">TechFlow</div>
          </div>
          <div class="glass-card p-6 flex items-center justify-center">
            <div class="text-white font-bold text-xl">DataCorp</div>
          </div>
          <div class="glass-card p-6 flex items-center justify-center">
            <div class="text-white font-bold text-xl">InnovateLab</div>
          </div>
          <div class="glass-card p-6 flex items-center justify-center">
            <div class="text-white font-bold text-xl">FinanceNext</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>