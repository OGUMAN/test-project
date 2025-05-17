<template>
  <div class="background-wrapper">
    <div class="background-text">
      <span>{{ repeatedText }}</span>
    </div>
  </div>
</template>

<script setup>
const baseText = ' FULL-CYCLE EVENT AGENCY\u00A0';
const repeatCount = 10;
const repeatedText = baseText.repeat(repeatCount);
</script>

<style lang="scss" scoped>
.background-wrapper {
  position: absolute;
  top: calc(50% + 40px);
  left: 50%;
  transform: translate(-50%, -50%) rotate(-30deg);
  overflow: hidden;
  white-space: nowrap;
  width: 120vw;
}

.background-text {
  z-index: 1;
  position: relative;
  display: inline-block;
  white-space: nowrap;
  font-size: 52px;
  font-weight: 700;
  animation: scroll-left 100s linear infinite;
  min-width: 200vw;

  color: transparent;
  -webkit-text-stroke: 1px #373737;
  text-stroke: 1px #373737;
  opacity: 0.1;
  font-style: italic;
  user-select: none;
}

@keyframes scroll-left {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}
</style>
