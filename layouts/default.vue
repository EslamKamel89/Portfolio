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
    <main class="p-2 mt-10">
      <slot />
    </main>
  </div>
</template>

<script setup lang="ts">
import { pr } from "~/Utils/pr";

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

const colorMode = useColorMode();
pr(colorMode.preference, "color preference");
onMounted(() => {
  colorMode.preference = "light";
});
</script>
<style>
body {
  @apply bg-white dark:bg-gray-900 text-gray-900 dark:text-gray-100;
}
</style>
