<template>
  <Title>{{ $t("name") }}</Title>
  <Meta
    name="description"
    content="Join the MOZGI event – an immersive experience with music, innovation, and creativity."
  />
  <Meta property="og:title" content="MOZGI Event" />
  <Meta
    property="og:description"
    content="Join the MOZGI event – an immersive experience with music, innovation, and creativity."
  />
  <Meta property="og:type" content="website" />
  <Header />
  <main>
    <NuxtPage />
    <PageTransitionSquare />
  </main>
</template>

<script lang="ts" setup>
useHead({
  htmlAttrs: {
    lang: "en",
  },
});
</script>

<style lang="scss">
@use "./components/header/style.scss" as headerStyle;
@import url("./assets/styles/main.scss");

body,
html {
  background: #bebebe;
  font-family: "TRYGrtsk", sans-serif;
  color: #373737;
}

*,
*:after,
*:before {
  box-sizing: border-box;
}

main {
  padding-top: headerStyle.$height;
}
</style>
