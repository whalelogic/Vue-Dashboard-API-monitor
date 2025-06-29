<script setup lang="ts">
import { ref, nextTick } from 'vue'

const terminalOutput = ref([
  { type: 'system', content: 'Whaler Systems Terminal v2.1.0' },
  { type: 'system', content: 'Connected to production cluster' },
  { type: 'prompt', content: 'whaler@systems:~$ ' },
])

const currentCommand = ref('')
const terminalRef = ref<HTMLElement>()

const executeCommand = async () => {
  if (!currentCommand.value.trim()) return
  
  // Add command to output
  terminalOutput.value.push({
    type: 'command',
    content: `whaler@systems:~$ ${currentCommand.value}`
  })
  
  // Simulate command execution
  const cmd = currentCommand.value.toLowerCase().trim()
  
  if (cmd === 'help') {
    terminalOutput.value.push({
      type: 'output',
      content: `Available commands:
  status    - Show system status
  deploy    - Deploy latest changes
  logs      - View system logs
  scale     - Scale services
  monitor   - System monitoring
  clear     - Clear terminal
  help      - Show this help`
    })
  } else if (cmd === 'status') {
    terminalOutput.value.push({
      type: 'output',
      content: `System Status:
  API Gateway: ✓ Online (CPU: 23%, Memory: 45%)
  ML Pipeline: ✓ Online (CPU: 67%, Memory: 78%)
  Data Processor: ⚠ Warning (CPU: 89%, Memory: 92%)
  Auth Service: ✓ Online (CPU: 12%, Memory: 34%)`
    })
  } else if (cmd === 'deploy') {
    terminalOutput.value.push({
      type: 'output',
      content: `Deploying to production...
  ✓ Building containers
  ✓ Running tests
  ✓ Pushing to registry
  ✓ Updating services
  Deployment completed successfully!`
    })
  } else if (cmd === 'logs') {
    terminalOutput.value.push({
      type: 'output',
      content: `[14:32:15] INFO  API-GW: Request processed successfully
[14:32:12] WARN  DATA-PROC: High memory usage detected
[14:32:08] INFO  ML-PIPE: Model inference completed
[14:32:05] ERROR AUTH: Failed authentication attempt`
    })
  } else if (cmd === 'clear') {
    terminalOutput.value = [
      { type: 'system', content: 'Whaler Systems Terminal v2.1.0' },
      { type: 'system', content: 'Connected to production cluster' },
    ]
  } else if (cmd.startsWith('scale')) {
    terminalOutput.value.push({
      type: 'output',
      content: `Scaling services...
  ✓ API Gateway: 3 → 5 instances
  ✓ ML Pipeline: 2 → 3 instances
  Scaling completed!`
    })
  } else {
    terminalOutput.value.push({
      type: 'error',
      content: `Command not found: ${currentCommand.value}. Type 'help' for available commands.`
    })
  }
  
  // Add new prompt
  terminalOutput.value.push({
    type: 'prompt',
    content: 'whaler@systems:~$ '
  })
  
  currentCommand.value = ''
  
  // Scroll to bottom
  await nextTick()
  if (terminalRef.value) {
    terminalRef.value.scrollTop = terminalRef.value.scrollHeight
  }
}
</script>

<template>
  <div class="p-6 h-full flex flex-col">
    <div class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-xl flex-1 flex flex-col overflow-hidden">
      <!-- Terminal Header -->
      <div class="flex items-center justify-between p-4 border-b border-white/10">
        <div class="flex items-center space-x-4">
          <div class="flex space-x-2">
            <div class="w-3 h-3 bg-red-400 rounded-full"></div>
            <div class="w-3 h-3 bg-yellow-400 rounded-full"></div>
            <div class="w-3 h-3 bg-cyber-400 rounded-full"></div>
          </div>
          <span class="text-white font-mono text-sm">Terminal</span>
        </div>
        <div class="flex items-center space-x-2">
          <div class="w-2 h-2 bg-cyber-400 rounded-full animate-pulse"></div>
          <span class="text-cyber-400 font-mono text-xs">CONNECTED</span>
        </div>
      </div>

      <!-- Terminal Content -->
      <div 
        ref="terminalRef"
        class="flex-1 p-4 bg-dark-900/50 font-mono text-sm overflow-auto"
      >
        <div 
          v-for="(line, index) in terminalOutput" 
          :key="index"
          :class="[
            'mb-1',
            line.type === 'system' ? 'text-cyber-400' :
            line.type === 'command' ? 'text-white' :
            line.type === 'output' ? 'text-white/80' :
            line.type === 'error' ? 'text-red-400' :
            'text-accent-400'
          ]"
        >
          <span v-if="line.type === 'output'" class="whitespace-pre-line">{{ line.content }}</span>
          <span v-else>{{ line.content }}</span>
        </div>
        
        <!-- Input Line -->
        <div class="flex items-center">
          <span class="text-accent-400 mr-2">whaler@systems:~$</span>
          <input
            v-model="currentCommand"
            @keyup.enter="executeCommand"
            class="flex-1 bg-transparent text-white outline-none"
            placeholder="Type a command..."
            autofocus
          />
        </div>
      </div>

      <!-- Quick Commands -->
      <div class="p-4 border-t border-white/10">
        <div class="flex flex-wrap gap-2">
          <button 
            @click="currentCommand = 'status'; executeCommand()"
            class="px-3 py-1 bg-cyber-500/20 text-cyber-400 rounded text-xs font-mono hover:bg-cyber-500/30 transition-colors"
          >
            status
          </button>
          <button 
            @click="currentCommand = 'deploy'; executeCommand()"
            class="px-3 py-1 bg-accent-500/20 text-accent-400 rounded text-xs font-mono hover:bg-accent-500/30 transition-colors"
          >
            deploy
          </button>
          <button 
            @click="currentCommand = 'logs'; executeCommand()"
            class="px-3 py-1 bg-primary-500/20 text-primary-400 rounded text-xs font-mono hover:bg-primary-500/30 transition-colors"
          >
            logs
          </button>
          <button 
            @click="currentCommand = 'help'; executeCommand()"
            class="px-3 py-1 bg-white/10 text-white/70 rounded text-xs font-mono hover:bg-white/20 transition-colors"
          >
            help
          </button>
          <button 
            @click="currentCommand = 'clear'; executeCommand()"
            class="px-3 py-1 bg-white/10 text-white/70 rounded text-xs font-mono hover:bg-white/20 transition-colors"
          >
            clear
          </button>
        </div>
      </div>
    </div>
  </div>
</template>