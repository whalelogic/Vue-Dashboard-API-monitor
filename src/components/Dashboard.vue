<script setup lang="ts">
import { ref } from 'vue'

const metrics = ref([
  { label: 'API Calls', value: '126', change: '+12%', color: 'accent' },
  { label: 'Active Systems', value: '4', change: '+3', color: 'primary' },
  { label: 'Uptime', value: '99.98%', change: '+0.02%', color: 'cyber' },
  { label: 'Response Time', value: '23ms', change: '-5ms', color: 'accent' }
])

const recentActivity = ref([
  { type: 'deploy', message: 'API Gateway v2.1 deployed', time: '2 min ago', status: 'success' },
  { type: 'alert', message: 'High CPU usage on Node-3', time: '5 min ago', status: 'warning' },
  { type: 'system', message: 'Auto-scaling triggered', time: '12 min ago', status: 'info' },
  { type: 'deploy', message: 'ML Model updated', time: '1 hour ago', status: 'success' }
])
</script>

<template>
  <div class="p-6 space-y-6 overflow-auto">
    <!-- Metrics Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
      <div 
        v-for="metric in metrics" 
        :key="metric.label"
        class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6 hover:bg-white/10 transition-all duration-300"
      >
        <div class="flex items-center justify-between mb-4">
          <h3 class="text-white/70 text-sm font-medium">{{ metric.label }}</h3>
          <div :class="[
            'w-3 h-3 rounded-full',
            metric.color === 'accent' ? 'bg-accent-400' : 
            metric.color === 'primary' ? 'bg-primary-400' : 'bg-cyber-400'
          ]"></div>
        </div>
        <div class="flex items-end justify-between">
          <div class="text-3xl font-bold text-white">{{ metric.value }}</div>
          <div :class="[
            'text-sm font-mono',
            metric.change.startsWith('+') ? 'text-cyber-400' : 'text-accent-400'
          ]">
            {{ metric.change }}
          </div>
        </div>
      </div>
    </div>

    <!-- Main Content Grid -->
    <div class="grid lg:grid-cols-3 gap-6">
      <!-- System Overview -->
      <div class="lg:col-span-2 bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
        <div class="flex items-center justify-between mb-6">
          <h2 class="text-xl font-bold text-white">System Overview</h2>
          <div class="flex space-x-2">
            <button class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded-lg text-sm font-mono">1H</button>
            <button class="px-3 py-1 bg-white/10 text-white/60 rounded-lg text-sm font-mono">24H</button>
            <button class="px-3 py-1 bg-white/10 text-white/60 rounded-lg text-sm font-mono">7D</button>
          </div>
        </div>
        
        <!-- Chart Placeholder -->
        <div class="h-64 bg-dark-900/50 rounded-lg border border-white/10 flex items-center justify-center">
          <div class="text-center">
            <div class="w-16 h-16 bg-gradient-to-br from-accent-500 to-primary-500 rounded-full mx-auto mb-4 flex items-center justify-center animate-pulse">
              <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/>
              </svg>
            </div>
            <p class="text-white/60">Real-time Analytics</p>
          </div>
        </div>
      </div>

      <!-- Activity Feed -->
      <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
        <h2 class="text-xl font-bold text-white mb-6">Recent Activity</h2>
        <div class="space-y-4">
          <div 
            v-for="activity in recentActivity" 
            :key="activity.message"
            class="flex items-start space-x-3 p-3 bg-white/5 rounded-lg border border-white/10"
          >
            <div :class="[
              'w-2 h-2 rounded-full mt-2 flex-shrink-0',
              activity.status === 'success' ? 'bg-cyber-400' :
              activity.status === 'warning' ? 'bg-yellow-400' : 'bg-primary-400'
            ]"></div>
            <div class="flex-1 min-w-0">
              <p class="text-white text-sm">{{ activity.message }}</p>
              <p class="text-white/50 text-xs font-mono mt-1">{{ activity.time }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Quick Actions -->
    <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
      <h2 class="text-xl font-bold text-white mb-6">Quick Actions</h2>
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
        <button class="p-4 bg-accent-500/10 border border-accent-400/30 rounded-lg hover:bg-accent-500/20 transition-all duration-300 group">
          <div class="w-8 h-8 bg-accent-500 rounded-lg mx-auto mb-3 flex items-center justify-center group-hover:scale-110 transition-transform">
            <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"/>
            </svg>
          </div>
          <div class="text-accent-400 font-medium text-sm">Deploy API</div>
        </button>
        
        <button class="p-4 bg-primary-500/10 border border-primary-400/30 rounded-lg hover:bg-primary-500/20 transition-all duration-300 group">
          <div class="w-8 h-8 bg-primary-500 rounded-lg mx-auto mb-3 flex items-center justify-center group-hover:scale-110 transition-transform">
            <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/>
            </svg>
          </div>
          <div class="text-primary-400 font-medium text-sm">View Metrics</div>
        </button>
        
        <button class="p-4 bg-cyber-500/10 border border-cyber-400/30 rounded-lg hover:bg-cyber-500/20 transition-all duration-300 group">
          <div class="w-8 h-8 bg-cyber-500 rounded-lg mx-auto mb-3 flex items-center justify-center group-hover:scale-110 transition-transform">
            <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"/>
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/>
            </svg>
          </div>
          <div class="text-cyber-400 font-medium text-sm">Settings</div>
        </button>
        
        <button class="p-4 bg-white/10 border border-white/20 rounded-lg hover:bg-white/20 transition-all duration-300 group">
          <div class="w-8 h-8 bg-white/20 rounded-lg mx-auto mb-3 flex items-center justify-center group-hover:scale-110 transition-transform">
            <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/>
            </svg>
          </div>
          <div class="text-white font-medium text-sm">Help</div>
        </button>
      </div>
    </div>
  </div>
</template>