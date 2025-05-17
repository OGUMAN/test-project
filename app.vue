<template>
  <Header />
  <main>
    <NuxtPage />
    <PageTransitionSquare />
  </main>
</template>

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
