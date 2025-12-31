<script setup>
const props = defineProps({
  isOpen: Boolean
});
const emit = defineEmits(['toggle'])
</script>

<template>
  <aside
    class="fixed inset-y-0 left-0 z-50 w-64 bg-gray-800 text-white transform transition-transform duration-300 ease-in-out overflow-y-auto"
    :class="{ '-translate-x-full': !props.isOpen }"
  >
    <div class="flex items-center justify-between h-16 px-6 bg-gray-900">
      <h2 class="text-xl font-semibold">Mon Sidebar</h2>
      <button @click="emit('toggle')" class="lg:hidden hover:bg-gray-600 p-2 rounded transition-all">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </div>

    <nav class="mt-8 px-4">
      <ul class="space-y-2">
        <li><a href="#" class="block px-4 py-3 rounded hover:bg-gray-700">Accueil</a></li>
        <li><a href="#" class="block px-4 py-3 rounded hover:bg-gray-700">Profil</a></li>
        <li><a href="#" class="block px-4 py-3 rounded hover:bg-gray-700">Paramètres</a></li>
        <li><a href="#" class="block px-4 py-3 rounded hover:bg-gray-700">Déconnexion</a></li>
      </ul>
    </nav>
  </aside>
</template>