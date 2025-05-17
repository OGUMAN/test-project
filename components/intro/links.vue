<template>
  <div class="intro-links">
    <BaseLink
      class="intro-links__link intro-links__link--left"
      :path="'where'"
      >{{ $t("navigation.where") }}</BaseLink
    >
    <BaseLink
      class="intro-links__link intro-links__link--right"
      :path="'what'"
      >{{ $t("navigation.what") }}</BaseLink
    >
    <BaseLink
      class="intro-links__link intro-links__link--bottom"
      :path="'who'"
      >{{ $t("navigation.who") }}</BaseLink
    >
  </div>
</template>

<style lang="scss" scoped>
.intro-links {
  width: 100%;
  height: 100%;
  position: absolute;
  z-index: 4;
  text-transform: lowercase;

  @media screen and (max-width: 728px) {
    display: none;
  }

  &__link {
    display: block;
    position: absolute;

    &--left {
      top: calc(50% + 40px);
      left: 30px;
      transform-origin: left top;
      transform: rotate(-90deg) translateY(-50%);
    }

    &--right {
      top: calc(50% + 40px);
      right: 30px;
      transform-origin: right top;
      transform: rotate(90deg) translateY(-50%);
    }

    &--bottom {
      left: 50%;
      transform: translateX(-50%);
      bottom: 19px;
    }
  }
}
</style>
