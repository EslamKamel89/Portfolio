<template>
  <div>We are inside a blog: {{ route.params.id }}</div>
</template>

<script setup lang="ts">
const route = useRoute();
</script>
