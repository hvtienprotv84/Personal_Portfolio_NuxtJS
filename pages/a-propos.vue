<template>
  <div>
    <div aria-hidden="true" class="fixed select-none font-black text-[#EDEDED] dark:text-neutral-900 -left-4 bottom-12 text-7xl
      sm:text-[8rem] md:-left-8 md:text-[11rem] lg:-left-12 lg:text-[15rem] xl:text-[18rem]">
      Experience.
    </div>
    <section class="relative max-w-3xl mx-auto mb-10">
      <h1 class="text-3xl lg:text-4xl font-black mb-14">Experience.</h1>
      <div class="flex gap-4 sm:gap-8">
        <div class="w-px shrink-0 bg-black dark:bg-white"></div>
        <div class="space-y-12">
          <div v-for="(info, index) in infos" :key="index">
            <div class="flex items-center -ml-6 sm:-ml-10 gap-3 sm:gap-6 mb-3">
              <div class="flex items-center justify-center size-4 bg-black dark:bg-white rounded-full">
                <div class="size-3 bg-white dark:bg-black rounded-full"></div>
              </div>
              <h2 class="text-lg lg:text-xl font-semibold" :id="info.id">
                {{ info.title }}
              </h2>
            </div>
            <p v-for="paragraph in info.content" v-html="paragraph"
              class="lg:text-lg leading-relaxed text-neutral-600 dark:text-neutral-300 mb-3">
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: "Tiến - Portfolio - NuxtJS | Experience",
  meta: [
    {
      name: "description",
      content:
        "Découvrez mon parcours, ma passion pour le web et l'accessibilité.",
    },
  ],
});

const infos = [
  {
    title: "Technology University.",
    content: [
      "Ngành Học: Công Nghệ Thông Tin",
      "Chuyên Ngành: Công Nghệ Phần Mềm",
      "GPA: 8.5/10"
    ],
  },
  {
    title: "Thực Tập Công Ty TNHH Giải Pháp và Công Nghệ.",
    content: [
      "Front-End Developer",
      "Công Nghệ Sử Dụng: ReactJS và Tailwind CSS",
      "Top 1 Sinh Viên Thực Tập Xuất Sắc Nhất.",
    ],
  }
];
</script>
