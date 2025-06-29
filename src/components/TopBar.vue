<script setup lang="ts">
import { ref } from 'vue'

defineProps<{
  activeView: string
}>()

const currentTime = ref(new Date().toLocaleTimeString())
const notifications = ref(3)

setInterval(() => {
  currentTime.value = new Date().toLocaleTimeString()
}, 1000)
</script>

<template>
  <div class="h-16 bg-dark-800 border-b border-white/10 flex items-center justify-between px-6">
    <!-- View Title -->
    <div class="flex items-center space-x-4">
      <h1 class="text-xl font-bold text-white capitalize">{{ activeView }}</h1>
      <div class="flex items-center space-x-2 px-3 py-1 bg-accent-500/10 border border-accent-400/30 rounded-full">
        <div class="w-2 h-2 bg-accent-400 rounded-full animate-pulse"></div>
        <span class="text-accent-400 font-mono text-xs">ACTIVE</span>
      </div>
    </div>

    <!-- Controls -->
    <div class="flex items-center space-x-6">
      <!-- Search -->
      <div class="relative">
        <input 
          type="text" 
          placeholder="Search systems..."
          class="w-64 px-4 py-2 bg-white/5 border border-white/20 rounded-lg text-white placeholder-white/50 focus:border-accent-400 focus:bg-white/10 transition-all duration-300"
        />
        <div class="absolute right-3 top-1/2 transform -translate-y-1/2">
          <svg class="w-4 h-4 text-white/50" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/>
          </svg>
        </div>
      </div>

      <!-- Notifications -->
      <button class="relative p-2 text-white/70 hover:text-white transition-colors">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-5 5v-5zM10.07 2.82l3.93 3.93-3.93 3.93-3.93-3.93 3.93-3.93z"/>
        </svg>
        <div v-if="notifications > 0" class="absolute -top-1 -right-1 w-5 h-5 bg-accent-500 rounded-full flex items-center justify-center">
          <span class="text-xs font-bold text-white">{{ notifications }}</span>
        </div>
      </button>

      <!-- Time -->
      <div class="text-white/70 font-mono text-sm">
        {{ currentTime }}
      </div>

      <!-- User Menu -->
      <div class="flex items-center space-x-3">
        <div class="w-8 h-8 bg-gradient-to-br from-accent-500 to-primary-500 rounded-full flex items-center justify-center">
          <span class="text-white font-bold text-sm">WS</span>
        </div>
      </div>
    </div>
  </div>
</template>