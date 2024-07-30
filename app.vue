<template>

  <Body
    class="overflow-x-hidden bg-white dark:bg-black text-black dark:text-white selection:bg-black selection:text-white dark:selection:bg-white dark:selection:text-black">
    <!-- Custom cursor -->
    <div id="outerCursor" aria-hidden="true"
      class="z-[9999] transition-all duration-[250ms] ease-out absolute -translate-x-1/2 -translate-y-1/2 size-20 rounded-full border border-black dark:border-white pointer-events-none"
      :class="{ 'mix-blend-difference bg-white size-32': isHovered }"
      :style="{ left: cursorPosition.x + 'px', top: cursorPosition.y + 'px' }" />
    <div id="innerCursor" aria-hidden="true"
      class="z-[9998] absolute -translate-x-1/2 -translate-y-1/2 size-2 rounded-full bg-black dark:bg-white pointer-events-none"
      :style="{ left: cursorPosition.x + 'px', top: cursorPosition.y + 'px' }" />

    <!-- Accessible link to go to the content -->
    <a href="#contenu" class="absolute -top-80 -left-80 focus:top-0 focus:left-4 bg-black text-white rounded-b-md p-1">
      Aller au contenu
    </a>

    <div class="min-h-dvh flex flex-col justify-between px-4 pt-8 pb-6 sm:px-12">
      <header class="max-w-6xl mx-auto w-full mb-20 md:mb-32 lg:mb-40 text-black dark:text-white">
        <nav class="flex justify-between items-center">
          <NuxtLink to="/">
            <img class="fill-black dark:fill-white w-[80px] h-[70px]" src="./public/logo_1.png"/>
            <span class="sr-only">Accueil</span>
          </NuxtLink>
          <div class="flex gap-6 sm:gap-8 items-center">
            <NuxtLink to="/a-propos" title="À propos"
              class="before:content-[''] before:absolute before:block before:w-full before:h-px before:top-6 before:left-0 before:bg-black before:dark:bg-white before:scale-x-0 before:transition-transform before:duration-300 hover:before:scale-x-100 relative">
              Experience
            </NuxtLink>
            <NuxtLink to="/projets" title="Blog"
              class="before:content-[''] before:absolute before:block before:w-full before:h-px before:top-6 before:left-0 before:bg-black before:dark:bg-white before:scale-x-0 before:transition-transform before:duration-300 hover:before:scale-x-100 relative">
              Projects
            </NuxtLink>
            <NuxtLink to="/skills" title="À propos"
              class="before:content-[''] before:absolute before:block before:w-full before:h-px before:top-6 before:left-0 before:bg-black before:dark:bg-white before:scale-x-0 before:transition-transform before:duration-300 hover:before:scale-x-100 relative">
              Skills
            </NuxtLink>
            <button class="mt-1" @click="toggleColorMode">
              <svg class="fill-inherit dark:fill-white" xmlns="http://www.w3.org/2000/svg" width="24" height="24"
                viewBox="0 0 24 24">
                <path
                  d="M0 12c0 6.627 5.373 12 12 12s12-5.373 12-12-5.373-12-12-12-12 5.373-12 12zm2 0c0-5.514 4.486-10 10-10v20c-5.514 0-10-4.486-10-10z">
                </path>
              </svg>
              <span class="sr-only">Activer/Désactiver le mode sombre</span>
            </button>
          </div>
        </nav>
      </header>

      <main id="contenu" class="mx-auto">
        <NuxtPage @cursor-hovered="isHovered = true" @cursor-left="isHovered = false" />
      </main>

      <footer
        class="max-w-6xl mx-auto w-full z-10 mt-20 md:mt-32 lg:mt-40 flex flex-wrap gap-x-8 gap-y-4 justify-between items-center">
        <NuxtLink :to="route.name === 'a-propos' ? '/projets' : '/a-propos' && route.name === 'projets' ? '/skills' : '/skills' && route.name === 'index' ? '/a-propos' : '/skills' && route.name === 'skills' ? '/' : '/'  " class="flex items-center w-fit">
          <span class="underline sm:no-underline hover:underline underline-offset-4 mr-2">
            {{
              route.name === 'a-propos'
                ? 'Projects'
                : route.name === 'projets'
                  ? 'Skills'
                  : route.name === 'skills'
                  ? 'Home'
                 : route.name === 'index'
                  ? 'Experience'
                  : 'Experience'
            }}
          </span>
          <svg class="animateSVG hidden size-7 sm:block fill-black dark:fill-white" aria-hidden="true"
            viewBox="0 0 24 24">
            <path fill-rule="evenodd"
              d="M16.72 7.72a.75.75 0 0 1 1.06 0l3.75 3.75a.75.75 0 0 1 0 1.06l-3.75 3.75a.75.75 0 1 1-1.06-1.06l2.47-2.47H3a.75.75 0 0 1 0-1.5h16.19l-2.47-2.47a.75.75 0 0 1 0-1.06Z"
              clip-rule="evenodd" />
          </svg>

        </NuxtLink>
        <div class="flex items-center gap-8">
          <NuxtLink to="/">
            <svg class="fill-black dark:fill-white size-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24">
              <path
                d="M4.98 3.5c0 1.381-1.11 2.5-2.48 2.5s-2.48-1.119-2.48-2.5c0-1.38 1.11-2.5 2.48-2.5s2.48 1.12 2.48 2.5zm.02 4.5h-5v16h5v-16zm7.982 0h-4.968v16h4.969v-8.399c0-4.67 6.029-5.052 6.029 0v8.399h4.988v-10.131c0-7.88-8.922-7.593-11.018-3.714v-2.155z">
              </path>
            </svg>
            <span class="sr-only">Accédez à mon profil LinkedIn.</span>
          </NuxtLink>
          <NuxtLink to="https://github.com/hvtienprotv84">
            <svg class="fill-black dark:fill-white size-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24">
              <path
                d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z">
              </path>
            </svg>
            <span class="sr-only">Accédez à mon profil GitHub.</span>
          </NuxtLink>
          <NuxtLink to="/">
            <svg class="fill-black dark:fill-white size-6" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24">
              <path d="M1.5 8.67v8.58a3 3 0 0 0 3 3h15a3 3 0 0 0 3-3V8.67l-8.928 5.493a3 3 0 0 1-3.144 0L1.5 8.67Z" />
              <path
                d="M22.5 6.908V6.75a3 3 0 0 0-3-3h-15a3 3 0 0 0-3 3v.158l9.714 5.978a1.5 1.5 0 0 0 1.572 0L22.5 6.908Z" />
            </svg>
            <span class="sr-only">Contactez-moi par email !.</span>
          </NuxtLink>
        </div>
      </footer>
    </div>
  </Body>
</template>

<script setup>
const colorMode = useColorMode();

const toggleColorMode = () => {
  colorMode.preference = colorMode.preference === "light" ? "dark" : "light";
};

const route = useRoute();

const cursorPosition = ref({ x: -200, y: -200 });

const isHovered = ref(false);

onMounted(() => {

  // Add an event listener for mousemove event
  if (window.innerWidth > 1200) {
    document.addEventListener("pointermove", (e) => {
      cursorPosition.value = { x: e.pageX, y: e.pageY };
    });
  }
});
</script>

<style>
/* Transition between pages */
.page-enter-active,
.page-leave-active {
  transition: all 0.5s;
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: blur(0.1rem);
}

/* SVG animation */
.animateSVG {
  animation-name: backAndForth;
  animation-duration: 0.7s;
  animation-iteration-count: infinite;
  animation-direction: alternate;

  @media (prefers-reduced-motion) {
    animation: none;
  }
}

@keyframes backAndForth {
  0% {
    margin-left: 0rem;
  }

  100% {
    margin-left: 1rem;
  }
}
</style>
