<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'

defineProps<{
  collapsed: boolean
  activeView: string
}>()

const emit = defineEmits<{
  setView: [view: string]
  toggleSidebar: []
}>()

const menuItems = [
  { id: 'dashboard', label: 'Dashboard', icon: 'grid' },
  { id: 'monitor', label: 'System Monitor', icon: 'activity' },
  { id: 'api', label: 'API Builder', icon: 'code' },
  { id: 'terminal', label: 'Terminal', icon: 'terminal' }
]
</script>

<template>
  <div :class="[
    'bg-dark-800 border-r border-white/10 transition-all duration-300 flex flex-col',
    collapsed ? 'w-16' : 'w-64'
  ]">
    <!-- Logo/Header -->
    <div class="p-4 border-b border-white/10">
      <div class="flex items-center space-x-3">
        <div class="w-8 h-8 bg-gradient-to-br from-accent-500 to-primary-500 rounded-lg flex items-center justify-center">
          <div class="w-4 h-4 bg-dark-900 rounded-sm flex items-center justify-center">
            <div class="w-2 h-2 bg-gradient-to-br from-accent-400 to-primary-400 rounded-full animate-pulse"></div>
          </div>
        </div>
        <div v-if="!collapsed" class="flex-1">
          <div class="text-white font-bold">Whaler</div>
          <div class="text-xs text-accent-400 font-mono">SYSTEMS</div>
        </div>
        <button 
          @click="emit('toggleSidebar')"
          class="w-6 h-6 text-white/60 hover:text-white transition-colors"
        >
          <svg fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
        </button>
      </div>
    </div>

    <!-- Navigation -->
    <nav class="flex-1 p-2">
      <div class="space-y-1">
        <button
          v-for="item in menuItems"
          :key="item.id"
          @click="emit('setView', item.id)"
          :class="[
            'w-full flex items-center space-x-3 px-3 py-2 rounded-lg transition-all duration-200',
            activeView === item.id 
              ? 'bg-accent-500/20 text-accent-400 border border-accent-400/30' 
              : 'text-white/70 hover:text-white hover:bg-white/5'
          ]"
        >
          <div class="w-5 h-5 flex-shrink-0">
            <svg v-if="item.icon === 'grid'" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z"/>
            </svg>
            <svg v-if="item.icon === 'activity'" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/>
            </svg>
            <svg v-if="item.icon === 'code'" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/>
            </svg>
            <svg v-if="item.icon === 'terminal'" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l3 3-3 3m5 0h3M5 20h14a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/>
            </svg>
          </div>
          <span v-if="!collapsed" class="font-medium">{{ item.label }}</span>
        </button>
      </div>
    </nav>

    <!-- Status Panel -->
    <div v-if="!collapsed" class="p-4 border-t border-white/10">
      <div class="space-y-3">
        <div class="flex items-center justify-between">
          <span class="text-xs text-white/60 font-mono">SYSTEM STATUS</span>
          <div class="w-2 h-2 bg-cyber-400 rounded-full animate-pulse"></div>
        </div>
        <div class="space-y-2">
          <div class="flex justify-between text-xs">
            <span class="text-white/60">CPU</span>
            <span class="text-cyber-400 font-mono">23%</span>
          </div>
          <div class="w-full bg-white/10 rounded-full h-1">
            <div class="bg-gradient-to-r from-cyber-500 to-cyber-400 h-1 rounded-full" style="width: 23%"></div>
          </div>
        </div>
        <div class="space-y-2">
          <div class="flex justify-between text-xs">
            <span class="text-white/60">Memory</span>
            <span class="text-primary-400 font-mono">67%</span>
          </div>
          <div class="w-full bg-white/10 rounded-full h-1">
            <div class="bg-gradient-to-r from-primary-500 to-primary-400 h-1 rounded-full" style="width: 67%"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>