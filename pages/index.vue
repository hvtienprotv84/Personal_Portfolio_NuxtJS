<template>
  <div class="w-fit mx-auto">
    <h1 @mouseover="$emit('cursor-hovered')" @mouseleave="$emit('cursor-left')"
      class="w-fit mx-auto lg:mt-[-200px] lg:p-4 mb-8 lg:mb-12 uppercase text-[45px] sm:text-7xl lg:text-[6rem] xl:text-[8rem] tracking-tight font-bold flex flex-col leading-none gap-4">
      <span>Xin Chào, Tôi là</span>
      <span class="md:ml-20">Huỳnh Vĩnh Tiến</span>
    </h1>
    <h2 class="text-4xl sm:text-center font-medium lg:mb-[-550px]">
      Software
      <NuxtLink to="https://github.com/hvtienprotv84"
        class="relative link after:text-white after:dark:text-black hover:after:content-['Engineer.'] after:bg-black after:dark:bg-white after:absolute after:left-0 after:bottom-0 after:w-full after:h-px after:transition-[height] hover:after:h-full">
        Engineer.
      </NuxtLink>
      <!-- WIP hover effect -->
    </h2>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: "Tiến - Portfolio - NuxtJS | Home",
  meta: [
    {
      name: "description",
      content:
        "Nicolas Walter est un développeur web d'interfaces pixel-perfect et accessibles, créateur de produits inclusifs et d'expériences digitales.",
    },
  ],
});

const emit = defineEmits(['cursor-left'])

onUnmounted(() => {
  emit('cursor-left')
});
</script>