<template>
  <div>hello world</div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: "Main Page",
  description: "This is Main Page",
  ogTitle: "Main Page",
  ogDescription: "[og:description]",
  ogImage: "[og:image]",
  ogUrl: "[og:url]",
  twitterTitle: "Main Page",
  twitterDescription: "[twitter:description]",
  twitterImage: "[twitter:image]",
  twitterCard: "summary",
});

useHead({
  title: "Main page",
  htmlAttrs: {
    lang: "en",
  },
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: "/favicon.png",
    },
  ],
});
</script>
