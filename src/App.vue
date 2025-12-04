<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'
const route = useRoute()
</script>

<template>
  <header v-if="route.name !== 'dating'">
    <div class="max-w-4xl mx-auto">
      <nav class="p-4 bg-gray-100 rounded-b-lg shadow-md flex space-x-4">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
        <RouterLink to="/dating">Dating App</RouterLink>
      </nav>
    </div>
  </header>

  <div v-if="route.name !== 'dating'" class="layout-default">
    <RouterView />
  </div>

  <div
    v-else
    class="w-screen min-h-screen fixed inset-0 bg-white overflow-auto"
  >
    <RouterView />
  </div>
</template>

<style>
.layout-default {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
</style>
