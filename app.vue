<template>
  <AppSeo />

  <Header />
  <main>
    <NuxtPage />
  </main>

  <AppTransition />
</template>

<style lang="scss">
@use "./components/header/style.scss" as headerStyle;
@import url("./assets/styles/main.scss");

main {
  padding-top: headerStyle.$height;
}
</style>
