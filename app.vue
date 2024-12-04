<script setup lang="ts">
import { Sonner } from "@/components/ui/sonner";

const colorMode = useColorMode();

const color = computed(() =>
  colorMode.value === "dark" ? "#09090b" : "#ffffff",
);

useHead({
  meta: [
    { charset: "utf-8" },
    { name: "viewport", content: "width=device-width, initial-scale=1" },
    { key: "theme-color", name: "theme-color", content: color },
  ],
  link: [{ rel: "icon", href: "/favicon.ico" }],
  htmlAttrs: {
    lang: "en",
  },
});

const title = "Nuxt Shadcn UI - Dashboard Template";
const description =
  "This dashboard, built with Nuxt, Shadcn UI, and UnoCSS. It includes a dark mode toggle and is optimized for performance and data efficiency.";

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  ogImage: "https://nuxt-shadcn-dashboard.vercel.app/social-card.png",
  twitterImage: "https://nuxt-shadcn-dashboard.vercel.app/social-card.png",
  twitterCard: "summary_large_image",
});
</script>

<template>
  <NuxtLayout vaul-drawer-wrapper>
    <NuxtPage />
  </NuxtLayout>

  <Toaster />
  <Sonner class="pointer-events-auto" />
</template>

<style>
@font-face {
  font-family: "Geist";
  src: url("/assets/fonts/geist/otf/Geist-Light.otf") format("otf");
  font-weight: 300;
  font-style: normal;
}

@font-face {
  font-family: "Geist";
  src: url("/assets/fonts/geist/otf/Geist-Regular.otf") format("otf");
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: "Geist";
  src: url("/assets/fonts/geist/otf/Geist-Medium.otf") format("otf");
  font-weight: 600;
  font-style: normal;
}

@font-face {
  font-family: "Geist";
  src: url("/assets/fonts/geist/otf/Geist-Bold.otf") format("otf");
  font-weight: 700;
  font-style: normal;
}

@font-face {
  font-family: "Geist";
  src: url("/assets/fonts/geist/otf/Geist-Black.otf") format("otf");
  font-weight: 900;
  font-style: normal;
}

* {
  @apply dark:border-[#313131];
}

html {
  font-family: "Geist", Roboto, sans-serif;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 600 !important;
  @apply dark:text-[#ddd];
}
</style>
