<template>
  <div class="container mx-auto px-2 max-w-3xl mt-5">
    <header class="flex justify-between items-center">
      <div>
        <NuxtLink to="/" class="text-2xl font-medium p-2 hover:bg-gray-200"
          >Eslam Kamel</NuxtLink
        >
      </div>
      <nav>
        <ul class="flex gap-x-2 font-mono">
          <li>
            <NuxtLink to="/">Home </NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about">About </NuxtLink>
          </li>
        </ul>
      </nav>
    </header>
    <main class="p-2">
      <slot />
    </main>
  </div>
</template>

<script setup lang="ts"></script>
