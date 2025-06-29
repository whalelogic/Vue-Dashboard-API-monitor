<script setup lang="ts">
import { ref } from 'vue'

const endpoints = ref([
  { method: 'GET', path: '/api/users', status: 'active', calls: '1.2K' },
  { method: 'POST', path: '/api/auth/login', status: 'active', calls: '890' },
  { method: 'PUT', path: '/api/users/:id', status: 'active', calls: '340' },
  { method: 'DELETE', path: '/api/users/:id', status: 'inactive', calls: '12' }
])

const selectedEndpoint = ref(endpoints.value[0])
const codeExample = ref(`{
  "method": "GET",
  "path": "/api/users",
  "headers": {
    "Authorization": "Bearer <token>",
    "Content-Type": "application/json"
  },
  "response": {
    "status": 200,
    "data": [
      {
        "id": 1,
        "name": "John Doe",
        "email": "john@example.com"
      }
    ]
  }
}`)
</script>

<template>
  <div class="p-6 space-y-6 overflow-auto">
    <!-- API Builder Header -->
    <div class="flex items-center justify-between">
      <div>
        <h1 class="text-2xl font-bold text-white">API Builder</h1>
        <p class="text-white/60">Design, test, and deploy your APIs</p>
      </div>
      <button class="px-6 py-3 bg-gradient-to-r from-accent-500 to-primary-500 text-white font-bold rounded-lg hover:scale-105 transition-all duration-300">
        Deploy API
      </button>
    </div>

    <div class="grid lg:grid-cols-3 gap-6">
      <!-- Endpoints List -->
      <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
        <div class="flex items-center justify-between mb-6">
          <h2 class="text-lg font-bold text-white">Endpoints</h2>
          <button class="w-8 h-8 bg-accent-500 rounded-lg flex items-center justify-center hover:scale-110 transition-transform">
            <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"/>
            </svg>
          </button>
        </div>
        
        <div class="space-y-2">
          <div 
            v-for="endpoint in endpoints" 
            :key="`${endpoint.method}-${endpoint.path}`"
            @click="selectedEndpoint = endpoint"
            :class="[
              'p-3 rounded-lg border cursor-pointer transition-all duration-300',
              selectedEndpoint === endpoint 
                ? 'bg-accent-500/20 border-accent-400/50' 
                : 'bg-white/5 border-white/10 hover:bg-white/10'
            ]"
          >
            <div class="flex items-center justify-between mb-2">
              <div class="flex items-center space-x-2">
                <span :class="[
                  'px-2 py-1 rounded text-xs font-mono',
                  endpoint.method === 'GET' ? 'bg-cyber-500/20 text-cyber-400' :
                  endpoint.method === 'POST' ? 'bg-accent-500/20 text-accent-400' :
                  endpoint.method === 'PUT' ? 'bg-primary-500/20 text-primary-400' :
                  'bg-red-500/20 text-red-400'
                ]">{{ endpoint.method }}</span>
                <div :class="[
                  'w-2 h-2 rounded-full',
                  endpoint.status === 'active' ? 'bg-cyber-400' : 'bg-white/30'
                ]"></div>
              </div>
              <span class="text-white/60 text-xs font-mono">{{ endpoint.calls }}</span>
            </div>
            <div class="text-white text-sm font-mono">{{ endpoint.path }}</div>
          </div>
        </div>
      </div>

      <!-- API Configuration -->
      <div class="lg:col-span-2 space-y-6">
        <!-- Endpoint Details -->
        <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
          <div class="flex items-center space-x-4 mb-6">
            <span :class="[
              'px-3 py-1 rounded font-mono font-bold',
              selectedEndpoint.method === 'GET' ? 'bg-cyber-500/20 text-cyber-400' :
              selectedEndpoint.method === 'POST' ? 'bg-accent-500/20 text-accent-400' :
              selectedEndpoint.method === 'PUT' ? 'bg-primary-500/20 text-primary-400' :
              'bg-red-500/20 text-red-400'
            ]">{{ selectedEndpoint.method }}</span>
            <span class="text-white font-mono text-lg">{{ selectedEndpoint.path }}</span>
            <div :class="[
              'px-2 py-1 rounded text-xs',
              selectedEndpoint.status === 'active' ? 'bg-cyber-500/20 text-cyber-400' : 'bg-white/20 text-white/60'
            ]">{{ selectedEndpoint.status }}</div>
          </div>

          <!-- Configuration Tabs -->
          <div class="flex space-x-4 mb-6 border-b border-white/10">
            <button class="px-4 py-2 text-accent-400 border-b-2 border-accent-400 font-medium">Request</button>
            <button class="px-4 py-2 text-white/60 hover:text-white transition-colors">Response</button>
            <button class="px-4 py-2 text-white/60 hover:text-white transition-colors">Security</button>
            <button class="px-4 py-2 text-white/60 hover:text-white transition-colors">Testing</button>
          </div>

          <!-- Code Editor -->
          <div class="bg-dark-900/50 rounded-lg border border-white/10 p-4">
            <div class="flex items-center justify-between mb-4">
              <div class="flex space-x-2">
                <div class="w-3 h-3 bg-red-400 rounded-full"></div>
                <div class="w-3 h-3 bg-yellow-400 rounded-full"></div>
                <div class="w-3 h-3 bg-cyber-400 rounded-full"></div>
              </div>
              <div class="flex space-x-2">
                <button class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded text-sm font-mono">Test</button>
                <button class="px-3 py-1 bg-primary-500/20 text-primary-400 rounded text-sm font-mono">Save</button>
              </div>
            </div>
            <pre class="text-white/80 font-mono text-sm overflow-auto h-64">{{ codeExample }}</pre>
          </div>
        </div>

        <!-- API Testing -->
        <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl p-6">
          <h3 class="text-lg font-bold text-white mb-4">Test Endpoint</h3>
          <div class="space-y-4">
            <div class="grid grid-cols-3 gap-4">
              <div>
                <label class="block text-white/70 text-sm mb-2">Method</label>
                <select class="w-full px-3 py-2 bg-white/5 border border-white/20 rounded-lg text-white">
                  <option>GET</option>
                  <option>POST</option>
                  <option>PUT</option>
                  <option>DELETE</option>
                </select>
              </div>
              <div class="col-span-2">
                <label class="block text-white/70 text-sm mb-2">URL</label>
                <input 
                  type="text" 
                  value="/api/users"
                  class="w-full px-3 py-2 bg-white/5 border border-white/20 rounded-lg text-white"
                />
              </div>
            </div>
            
            <div class="flex space-x-4">
              <button class="px-6 py-2 bg-accent-500 text-white rounded-lg hover:bg-accent-600 transition-colors">
                Send Request
              </button>
              <button class="px-6 py-2 bg-white/10 text-white rounded-lg hover:bg-white/20 transition-colors">
                Clear
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>