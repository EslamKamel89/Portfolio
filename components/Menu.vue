<template>
  <nav>
    <ul class="flex gap-x-2 font-mono">
      <li>
        <NuxtLink id="link" to="/">Home </NuxtLink>
      </li>
      <li>
        <NuxtLink id="link" to="/about">About </NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts"></script>
<style scoped>
#link {
  @apply p-1 hover:bg-gray-100;
}
</style>
