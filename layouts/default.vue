<template>
  <div class="container mx-auto px-2 max-w-3xl mt-5">
    <header class="flex justify-between items-center">
      <div>
        <NuxtLink to="/" class="text-2xl font-medium p-2 hover:bg-gray-200"
          >Eslam Kamel</NuxtLink
        >
      </div>
      <Menu />
    </header>
    <main class="p-2">
      <slot />
    </main>
  </div>
</template>

<script setup lang="ts">
// import Menu from "~/components/Menu.vue";
</script>
