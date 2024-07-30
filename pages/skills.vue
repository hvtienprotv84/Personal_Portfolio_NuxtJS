<template>
  <p class="text-5xl mb-[30px]">Skills.</p>
  <div class="flex flex-wrap gap-2 max-w-[800px]">
    <span v-for="(technology, index) in skills.technology" :key="index"
      class="bg-neutral-200 rounded-full px-2 text-neutral-700 dark:bg-neutral-700 dark:text-neutral-200">
      {{ technology }}
    </span>
  </div>
</template>

<script setup lang="ts">

import skills from "~/assets/data/skills.json";

useHead({
  title: "Tiến - Portfolio - NuxtJS | Skills",
  meta: [
    {
      name: "description",
      content: "Mes projets personnels et universitaires.",
    },
  ],
});


</script>
