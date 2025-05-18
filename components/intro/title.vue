<template>
  <BaseMouseTilt class="intro-title">
    <h1 class="intro-title__text">{{ $t("intro.title") }}</h1>
  </BaseMouseTilt>
</template>

<style lang="scss" scoped>
.intro-title {
  position: relative;
  z-index: 7;

  &__text {
    margin: 0;
    font-size: 82px;
    font-weight: bold;
    text-align: center;
    position: relative;
    z-index: 6;
    will-change: transform;
    max-width: 1100px;
    padding: 0 30px;
    text-transform: uppercase;

    @media screen and (max-width: 1124px) {
      font-size: 58px;
      max-width: 900px;
    }

    @media screen and (max-width: 768px) {
      max-width: 608px;
      padding: 0;
    }

    @media screen and (max-width: 560px) {
      font-size: 34px;
      max-width: 400px;
    }
  }
}
</style>
