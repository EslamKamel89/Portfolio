<template>
  <div class="container mx-auto px-2 max-w-3xl mt-5">
    <header class="flex justify-between items-center">
      <div class="flex gap-x-12 items-center">
        <NuxtLink to="/" class="text-2xl font-medium p-2 hover:bg-gray-200"
          >Eslam Kamel</NuxtLink
        >
        <Menu />
      </div>
      <ColorModeSelector />
    </header>
    <main class="p-2 mt-10">
      <slot />
    </main>
  </div>
</template>

<script setup lang="ts">
useHead({
  bodyAttrs: { style: { fontFamily: "Roboto" } },
  titleTemplate: (title) => {
    return title ? `${title} - Eslam Kamel` : "Eslam Kamel";
  },
  link: [
    {
      rel: "preconnect",
      href: "https://fonts.googleapis.com",
    },
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/css2?family=Roboto&display=swap",
      crossorigin: "",
    },
  ],
});
</script>
<style>
body {
  @apply bg-white dark:bg-gray-900 text-gray-900 dark:text-gray-100;
}
</style>
