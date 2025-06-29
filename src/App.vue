<script setup lang="ts">
import Sidebar from './components/Sidebar.vue'
import TopBar from './components/TopBar.vue'
import Dashboard from './components/Dashboard.vue'
import Terminal from './components/Terminal.vue'
import SystemMonitor from './components/SystemMonitor.vue'
import ApiBuilder from './components/ApiBuilder.vue'
import { ref } from 'vue'

const activeView = ref('dashboard')
const sidebarCollapsed = ref(false)

const setActiveView = (view: string) => {
  activeView.value = view
}

const toggleSidebar = () => {
  sidebarCollapsed.value = !sidebarCollapsed.value
}
</script>

<template>
  <div class="h-screen bg-dark-900 flex overflow-hidden">
    <!-- Sidebar -->
    <Sidebar 
      :collapsed="sidebarCollapsed"
      :activeView="activeView"
      @setView="setActiveView"
      @toggleSidebar="toggleSidebar"
    />
    
    <!-- Main Content Area -->
    <div class="flex-1 flex flex-col min-w-0">
      <!-- Top Bar -->
      <TopBar :activeView="activeView" />
      
      <!-- Content Views -->
      <div class="flex-1 overflow-hidden">
        <Dashboard v-if="activeView === 'dashboard'" />
        <SystemMonitor v-if="activeView === 'monitor'" />
        <ApiBuilder v-if="activeView === 'api'" />
        <Terminal v-if="activeView === 'terminal'" />
      </div>
    </div>
  </div>
</template>