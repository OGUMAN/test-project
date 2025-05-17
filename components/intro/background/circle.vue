<template>
  <div class="intro-circle">
    <div class="intro-circle__circle"></div>
    <IntroCircularText />
  </div>
</template>

<style lang="scss" scoped>
$size: 580px;
$small-size: 294px;

.intro-circle {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 5;

  &__circle {
    width: $size;
    height: $size;
    background-color: #ffcb46;
    filter: blur(38px);
    border-radius: 50%;

    @media screen and (max-width: 560px) {
      width: $small-size;
      height: $small-size;
    }
  }
}
</style>
