<script setup>
const emit = defineEmits(["toggle"]);
</script>

<template>
  <header class="bg-white shadow-sm h-16 flex items-center px-6">
    <button @click="emit('toggle')" class="hover:bg-gray-200 p-2 rounded transition-all">
      <svg
        class="w-6 h-6"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16M4 18h16"
        />
      </svg>
    </button>
    <h1 class="ml-6 text-2xl font-semibold">Contenu Principal</h1>
  </header>
</template>
