<template>
  <Title>{{ $t("meta.title") }}</Title>
  <Meta name="description" :content="$t('meta.description')" />
  <Meta property="og:title" content="MOZGI Event" />
  <Meta property="og:description" :content="$t('meta.description')" />
  <Meta property="og:type" content="website" />
</template>

<script lang="ts" setup>
useHead({
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: "/favicon-96x96.png",
      sizes: "96x96",
    },
    { rel: "icon", type: "image/svg+xml", href: "/favicon.svg" },
    { rel: "shortcut icon", href: "/favicon.ico" },
    {
      rel: "apple-touch-icon",
      sizes: "180x180",
      href: "/apple-touch-icon.png",
    },
    { rel: "manifest", href: "/site.webmanifest" },
  ],
  meta: [{ name: "apple-mobile-web-app-title", content: "Mozgi" }],
  lang: "en",
});
</script>
