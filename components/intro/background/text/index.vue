<template>
  <IntroBackgroundTextLine />
  <div class="flipped">
    <IntroBackgroundTextLine />
  </div>
</template>

<style lang="scss" scoped>
.flipped {
  transform: rotate(180deg);
  position: absolute;
}
</style>
