<script setup>
import ButtonRepo from '@/components/ButtonRepo.vue'
</script>

<template>
  <div class="bg-gray-50">
    <div
      class="mx-auto max-w-screen-xl px-4 py-12 sm:px-6 lg:items-center lg:justify-between lg:py-16 lg:px-8"
    >
      <h1
        class="text-3xl font-extrabold leading-9 tracking-tight text-gray-900 sm:text-7xl sm:leading-15"
      >
        <span class="text-indigo-600">Dedicated</span>
        and
        <span class="text-indigo-600">Obsessive</span> 
        Developer and Designer
      </h1>
      <div class="py-8"></div>
      <div class="inline-flex rounded-md shadow">
        <router-link
          to="/about"
          class="inline-flex items-center justify-center rounded-md border border-transparent bg-indigo-600 px-5 py-3 text-base font-medium leading-6 text-white transition duration-150 ease-in-out hover:bg-indigo-500 focus:outline-none"
          >Contact Me</router-link
        >
      </div>
      <ButtonRepo />
    </div>
  </div>
</template>
