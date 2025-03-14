<template>
  <button
    @click="toggleMode"
    class="hover:bg-gray-100 dark:hover:bg-gray-500 p-2 rounded-full"
  >
    <div
      class="flex gap-x-2 items-center"
      @mouseenter="showNextModeLabel = true"
      @mouseleave="showNextModeLabel = false"
    >
      <div class="text-xs" v-if="showNextModeLabel">
        Switch to {{ nextMode }}
      </div>
      <div>
        <span v-if="nextMode == 'light'">☀️</span>
        <span v-else-if="nextMode == 'dark'">🌙</span>
        <span v-else>💻</span>
      </div>
    </div>
  </button>
</template>

<script setup lang="ts">
type ColorThemeMode = "light" | "dark" | "system";
const modes: ColorThemeMode[] = ["light", "dark", "system"];
const colorMode = useColorMode();
const showNextModeLabel = ref<boolean>(false);
onMounted(() => {
  colorMode.preference = "dark";
});
const nextMode = computed<ColorThemeMode>(() => {
  if (colorMode.preference == "light") return "dark";
  if (colorMode.preference == "dark") return "system";
  if (colorMode.preference == "system") return "light";
  return "light";
});
const toggleMode = () => (colorMode.preference = nextMode.value ?? "light");
</script>
