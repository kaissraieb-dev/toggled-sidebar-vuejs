<script setup>
import { ref } from "vue";
import Sidebar from "./layout/Sidebar.vue";
import Header from "./layout/Header.vue";
import MainContent from "./components/MainContent.vue";

const sidebarOpen = ref(true); // ouverte par défaut

const toggleSidebar = () => {
  sidebarOpen.value = !sidebarOpen.value;
};
</script>

<template>
  <div class="min-h-screen flex flex-col bg-gray-50">
    <!-- Overlay mobile uniquement -->
    <div
      v-if="sidebarOpen"
      class="fixed inset-0 bg-gray-900/50 z-40 lg:hidden"
      @click="toggleSidebar"
    />

    <!-- Sidebar -->
    <Sidebar :is-open="sidebarOpen" @toggle="toggleSidebar" />

    <!-- Contenu principal avec padding responsive -->
    <div
      class="flex-1 flex flex-col transition-padding-left duration-300 ease-in-out"
      :class="{ 'lg:pl-64': sidebarOpen }"
    >
      <Header @toggle="toggleSidebar" />
      <MainContent />
    </div>
  </div>
</template>
