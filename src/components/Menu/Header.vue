<template>
    <header class="bg-blue-500 h-16 w-full px-8 py-2 flex items-center justify-between">
        <div class="text-xl font-semibold text-gray-50">
            <span>Vue Code Refactor</span>
        </div>

        <div class="flex items-center space-x-6">
            <NavLink to="/">Home</NavLink>
            <NavLink to="/about">About</NavLink>
        </div>
    </header>
</template>

<script setup>
import NavLink from './NavLink.vue'
</script>

