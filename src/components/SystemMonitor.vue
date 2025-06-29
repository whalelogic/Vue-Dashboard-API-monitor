<script setup lang="ts">
import { ref } from 'vue'

const systems = ref([
  { name: 'API Gateway', status: 'online', cpu: 23, memory: 45, requests: '1.2K/min' },
  { name: 'ML Pipeline', status: 'online', cpu: 67, memory: 78, requests: '340/min' },
  { name: 'Data Processor', status: 'warning', cpu: 89, memory: 92, requests: '890/min' },
  { name: 'Auth Service', status: 'online', cpu: 12, memory: 34, requests: '2.1K/min' }
])

const logs = ref([
  { time: '14:32:15', level: 'INFO', service: 'API-GW', message: 'Request processed successfully' },
  { time: '14:32:12', level: 'WARN', service: 'DATA-PROC', message: 'High memory usage detected' },
  { time: '14:32:08', level: 'INFO', service: 'ML-PIPE', message: 'Model inference completed' },
  { time: '14:32:05', level: 'ERROR', service: 'AUTH', message: 'Failed authentication attempt' }
])
</script>

<template>
  <div class="p-6 space-y-6 overflow-auto">
    <!-- System Status Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
      <div 
        v-for="system in systems" 
        :key="system.name"
        class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6"
      >
        <div class="flex items-center justify-between mb-4">
          <h3 class="text-white font-medium">{{ system.name }}</h3>
          <div :class="[
            'w-3 h-3 rounded-full',
            system.status === 'online' ? 'bg-cyber-400 animate-pulse' : 'bg-yellow-400'
          ]"></div>
        </div>
        
        <div class="space-y-3">
          <div>
            <div class="flex justify-between text-xs mb-1">
              <span class="text-white/60">CPU</span>
              <span class="text-white font-mono">{{ system.cpu }}%</span>
            </div>
            <div class="w-full bg-white/10 rounded-full h-2">
              <div 
                :class="[
                  'h-2 rounded-full transition-all duration-500',
                  system.cpu > 80 ? 'bg-gradient-to-r from-red-500 to-red-400' :
                  system.cpu > 60 ? 'bg-gradient-to-r from-yellow-500 to-yellow-400' :
                  'bg-gradient-to-r from-cyber-500 to-cyber-400'
                ]"
                :style="`width: ${system.cpu}%`"
              ></div>
            </div>
          </div>
          
          <div>
            <div class="flex justify-between text-xs mb-1">
              <span class="text-white/60">Memory</span>
              <span class="text-white font-mono">{{ system.memory }}%</span>
            </div>
            <div class="w-full bg-white/10 rounded-full h-2">
              <div 
                :class="[
                  'h-2 rounded-full transition-all duration-500',
                  system.memory > 80 ? 'bg-gradient-to-r from-red-500 to-red-400' :
                  system.memory > 60 ? 'bg-gradient-to-r from-yellow-500 to-yellow-400' :
                  'bg-gradient-to-r from-primary-500 to-primary-400'
                ]"
                :style="`width: ${system.memory}%`"
              ></div>
            </div>
          </div>
          
          <div class="pt-2 border-t border-white/10">
            <div class="text-xs text-white/60">Requests</div>
            <div class="text-accent-400 font-mono text-sm">{{ system.requests }}</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Monitoring Dashboard -->
    <div class="grid lg:grid-cols-3 gap-6">
      <!-- Real-time Logs -->
      <div class="lg:col-span-2 bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
        <div class="flex items-center justify-between mb-6">
          <h2 class="text-xl font-bold text-white">System Logs</h2>
          <div class="flex space-x-2">
            <button class="px-3 py-1 bg-cyber-500/20 text-cyber-400 rounded-lg text-sm font-mono">LIVE</button>
            <button class="px-3 py-1 bg-white/10 text-white/60 rounded-lg text-sm font-mono">PAUSE</button>
          </div>
        </div>
        
        <div class="bg-dark-900/50 rounded-lg border border-white/10 p-4 h-80 overflow-auto font-mono text-sm">
          <div 
            v-for="log in logs" 
            :key="`${log.time}-${log.message}`"
            class="flex items-start space-x-4 py-2 border-b border-white/5 last:border-b-0"
          >
            <span class="text-white/50 text-xs">{{ log.time }}</span>
            <span :class="[
              'text-xs px-2 py-1 rounded',
              log.level === 'INFO' ? 'bg-cyber-500/20 text-cyber-400' :
              log.level === 'WARN' ? 'bg-yellow-500/20 text-yellow-400' :
              'bg-red-500/20 text-red-400'
            ]">{{ log.level }}</span>
            <span class="text-accent-400 text-xs">{{ log.service }}</span>
            <span class="text-white/70 text-xs flex-1">{{ log.message }}</span>
          </div>
        </div>
      </div>

      <!-- System Controls -->
      <div class="space-y-6">
        <!-- Quick Controls -->
        <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
          <h3 class="text-lg font-bold text-white mb-4">Quick Controls</h3>
          <div class="space-y-3">
            <button class="w-full p-3 bg-cyber-500/10 border border-cyber-400/30 rounded-lg hover:bg-cyber-500/20 transition-all duration-300 text-cyber-400 font-medium">
              Restart All Services
            </button>
            <button class="w-full p-3 bg-accent-500/10 border border-accent-400/30 rounded-lg hover:bg-accent-500/20 transition-all duration-300 text-accent-400 font-medium">
              Scale Up
            </button>
            <button class="w-full p-3 bg-yellow-500/10 border border-yellow-400/30 rounded-lg hover:bg-yellow-500/20 transition-all duration-300 text-yellow-400 font-medium">
              Maintenance Mode
            </button>
          </div>
        </div>

        <!-- Alerts -->
        <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
          <h3 class="text-lg font-bold text-white mb-4">Active Alerts</h3>
          <div class="space-y-3">
            <div class="p-3 bg-yellow-500/10 border border-yellow-400/30 rounded-lg">
              <div class="flex items-center space-x-2 mb-2">
                <div class="w-2 h-2 bg-yellow-400 rounded-full"></div>
                <span class="text-yellow-400 font-medium text-sm">High CPU Usage</span>
              </div>
              <p class="text-white/70 text-xs">Data Processor at 89%</p>
            </div>
            
            <div class="p-3 bg-red-500/10 border border-red-400/30 rounded-lg">
              <div class="flex items-center space-x-2 mb-2">
                <div class="w-2 h-2 bg-red-400 rounded-full animate-pulse"></div>
                <span class="text-red-400 font-medium text-sm">Auth Failures</span>
              </div>
              <p class="text-white/70 text-xs">Multiple failed attempts detected</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>