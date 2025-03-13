<template>
  <p class="mb-5">Take a look at my GitHub projects!</p>
  <div v-if="status.toString() == 'pending'">Pending</div>
  <div v-else-if="status.toString() == 'error'">
    Someting Went wrong... please try again later
  </div>
  <div v-else-if="status.toString() == 'success'">
    <ul class="grid grid-cols-1 gap-4">
      <li
        v-for="project in projects"
        :key="project.id"
        class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono"
      >
        <a :href="project.html_url" target="_blank" class="w-full inline-block">
          <div class="flex items-center justify-between">
            <div class="font-semibold">{{ project.name }}</div>
            <div>{{ project.stargazers_count }} ⭐</div>
          </div>
          <p class="text-sm">{{ project.description }}</p>
        </a>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import type { Project } from "~/types/types";

const { data, error, execute, refresh, status } = useFetch<Project[]>(
  "https://api.github.com/users/EslamKamel89/repos"
);
const projects = computed(() => {
  data.value?.map((project) => {
    project.stargazers_count = Math.floor(Math.random() * 4 + 1);
    return project;
  });
  return data.value?.sort(
    (projectA, projectB) =>
      projectB.stargazers_count - projectA.stargazers_count
  );
});
</script>
