<template>
  <p class="mb-5">Take a look at my GitHub projects!</p>
  <div v-if="status.toString() == 'pending'">Pending</div>
  <div v-else-if="status.toString() == 'error'">
    Someting Went wrong... please try again later
  </div>
  <div v-else-if="status.toString() == 'success'">Success</div>
</template>

<script setup lang="ts">
const { data, error, execute, refresh, status } = useFetch(
  "https://api.github.com/users/EslamKamel89/repos"
);
</script>
