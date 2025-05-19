<template>
  <section class="intro content">
    <IntroBackground />
    <IntroLinks />
    <BaseFadeIn>
      <IntroTitle />
    </BaseFadeIn>
  </section>
</template>

<style lang="scss" scoped>
@use "~/components/header/style.scss" as headerStyle;

.intro {
  height: 100vh;
  margin-top: - headerStyle.$height;
  display: flex;
  align-items: center;
  justify-content: center;

  position: relative;
  overflow: hidden;
}
</style>
