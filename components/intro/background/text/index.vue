<template>
  <div>
    <IntroBackgroundTextLine class="background-text__line" />
  </div>
  <div class="background-text__line--flipped">
    <IntroBackgroundTextLine />
  </div>
</template>

<style lang="scss" scoped>
.background-text {
  &__line {
    &--flipped {
      transform: rotate(180deg);
      position: absolute;
    }
  }
}

@media screen and (max-width: 561px) {
  :deep(.background-wrapper) {
    transform: translate(-50%, -50%) rotate(-57deg);
  }
}
</style>
