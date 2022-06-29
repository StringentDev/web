<script setup>
import NavBar from '@/components/NavBar.vue'
</script>

<template>
  <div class="dark:bg-black">
    <NavBar></NavBar>
    <main>
      <router-view />
    </main>
  </div>
</template>
