<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { defineAsyncComponent } from 'vue'
const Header = defineAsyncComponent(() => import('@/components/Menu/Header.vue'))
</script>

<template>
  <Header />

  <main class="max-w-xl mx-auto p-4">
    <RouterView />
  </main>

</template>

