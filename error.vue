<template>
  <Body class="bg-white p-3">
    <main
      id="contenu"
      class="min-h-dvh flex flex-col items-center justify-center gap-12"
    >
      <div>
        <h1 class="text-3xl mb-3">On dirait que quelque chose ne va pas...</h1>
        <p class="text-xl" v-if="error">{{ error.message }}</p>
      </div>
      <NuxtLink
        to="/"
        class="bg-black text-white px-4 py-2 rounded-sm font-medium text-lg"
        >Retourner à l'accueil</NuxtLink
      >
    </main>
  </Body>
</template>

<script setup lang="ts">
import { useError } from "#app";

const error = useError();
</script>
