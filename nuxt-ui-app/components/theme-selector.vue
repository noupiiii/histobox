<template>
    <div @click="toggleTheme">
        <UButton square variant="ghost">
          <UIcon name="i-heroicons-sun-solid" class="h-5 w-5" v-if="isDarkMode" />
          <UIcon name="i-heroicons-moon-solid" class="h-5 w-5" v-else />
        </UButton>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  const isDarkMode = ref(false);
  
  const toggleTheme = () => {
    isDarkMode.value = !isDarkMode.value;
    const root = document.documentElement;
    if (isDarkMode.value) {
      root.classList.add('dark');
    } else {
      root.classList.remove('dark');
    }
  };
  
  const initializeTheme = () => {
    isDarkMode.value = document.documentElement.classList.contains('dark');
  };
  
  onMounted(() => {
    initializeTheme();
  });
  </script>