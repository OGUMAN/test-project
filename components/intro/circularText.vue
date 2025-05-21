<template>
  <svg
    :width="size"
    :height="size"
    :viewBox="`0 0 ${size} ${size}`"
    class="intro-orbit-text"
  >
    <!-- Center dot -->
    <circle :cx="center" :cy="center" :r="dotRadius" :fill="dotColor" />

    <!-- Rotating characters -->
    <g class="intro-orbit-text__group">
      <template v-for="(char, i) in characters" :key="i">
        <text
          class="intro-orbit-text__text"
          :x="getCharX(i)"
          :y="getCharY(i)"
          :transform="`rotate(${getCharRotation(i)} ${getCharX(i)} ${getCharY(
            i
          )})`"
          :font-size="fontSize"
          text-anchor="middle"
          dominant-baseline="middle"
        >
          {{ char }}
        </text>
      </template>
    </g>
  </svg>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  text: { type: String, default: "showreel showreel showreel" },
  size: { type: Number, default: 130 },
  radius: { type: Number, default: 55 },
  fontSize: { type: Number, default: 11 },
  letterSpacing: { type: Number, default: 12 }, // in pixels
  dotRadius: { type: Number, default: 5 },
  dotColor: { type: String, default: "#000000" },
});

const center = computed(() => props.size / 2);
const characters = computed(() => props.text.split(""));

// Angle step based on arc length spacing
const angleStep = computed(
  () => (props.letterSpacing / props.radius) * (180 / Math.PI)
); // degrees

const getCharAngle = (i) => i * angleStep.value;

const getCharX = (i) =>
  center.value + props.radius * Math.cos((getCharAngle(i) * Math.PI) / 180);
const getCharY = (i) =>
  center.value + props.radius * Math.sin((getCharAngle(i) * Math.PI) / 180);

const getCharRotation = (i) => getCharAngle(i) + 90;
</script>

<style scoped lang="scss">
.intro-orbit-text {
  display: block;
  margin: auto;
  position: absolute;
  z-index: 6;
  bottom: 20px;
  display: block;
  width: inherit;
  right: 20px;
  user-select: none;

  &__group {
    transform-origin: center;
    transition: transform 2s ease;
    transform: rotate(90deg);
  }

  &:hover &__group {
    transition: transform 4s ease;
    transform: rotate(-360deg);
  }

  &__text {
    fill: #ffffff;
  }

  @media screen and (max-width: 560px) {
    bottom: -70px;
    right: 0;
  }
}
</style>
