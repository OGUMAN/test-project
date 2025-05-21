<template>
  <div class="lang-wrapper" @mouseleave="hideLangOptions">
    <div class="lang" @mouseenter="showLangOptions">
      <img class="lang__icon" src="./image.png" alt="Tongue icon" />
    </div>
    <div class="lang-options" ref="options">
      <span
        v-for="(label, index) in labels"
        :key="label"
        class="lang-option"
        :style="getPositionStyle(index)"
        :class="{ active: isActive(locales[index]) }"
        @click="changeLang(locales[index])"
      >
        {{ label }}
      </span>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import { useI18n } from "vue-i18n";
import { gsap } from "gsap";

const { locale } = useI18n();

const options = ref<HTMLElement | null>(null);
const isOpened = ref(false);

const labels: string[] = ["EN", "UK", "ES"];
const locales: string[] = ["en", "uk", "es"];

const getPositionStyle = (index: number): Record<string, string> => {
  const angle = -35 + index * 28;
  const rad = (angle * Math.PI) / 180;
  const x = 30 * Math.cos(rad);
  const y = 30 * Math.sin(rad);
  const isBottomHalf = angle > 90 || angle < -90;
  const rotation = angle + (isBottomHalf ? 180 : 0);

  return {
    transform: `translate(${x}px, ${y}px) rotate(${rotation}deg)`,
    transformOrigin: "left center",
  };
};

function showLangOptions(): void {
  if (!options.value && isOpened.value) return;
  isOpened.value = true;

  const children = Array.from(options.value.children) as HTMLElement[];

  gsap.killTweensOf(children);
  gsap.fromTo(
    children,
    { opacity: 0, scale: 0.5 },
    {
      opacity: 1,
      scale: 1,
      stagger: 0.2,
      duration: 0.6,
      ease: "back.out(1.7)",
    }
  );
}

function hideLangOptions(): void {
  if (!options.value) return;
  isOpened.value = false;

  const children = Array.from(options.value.children) as HTMLElement[];

  gsap.killTweensOf(children);
  gsap.to(children, {
    opacity: 0,
    scale: 0.5,
    duration: 0.2,
    stagger: -0.05,
    ease: "power1.in",
  });
}

function changeLang(lang: string): void {
  locale.value = lang;
  hideLangOptions();
}

function isActive(langCode: string): boolean {
  return locale.value === langCode;
}
</script>

<style lang="scss" scoped>
$size: 38px;

.lang-wrapper {
  position: relative;
  padding-right: 60px;
  padding-top: 30px;
  padding-bottom: 30px;
  width: fit-content;
  display: flex;
  align-items: center;
  justify-content: center;

  .lang {
    height: $size;
    width: $size;
    border-radius: 50%;
    border: 1px solid rgba(255, 255, 255, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: transform .2s;

    &__icon {
      width: 15px;
      transition: transform 0.2s;
      transform: translateY(1px);
    }

    &:hover {
      transform: translateY(-2px) scale(110%);
    }
  }

  .lang-options {
    position: absolute;
    top: calc(50% - 7px);
    transform: translate(-50%, -50%);

    .lang-option {
      transition: color 0.2s, font-size 0.2s;
      position: absolute;
      top: 0;
      left: 0;
      transform: translate(0, 0);
      padding: 3px 6px;
      border-radius: 10px;
      font-size: 12px;
      font-weight: 500;
      opacity: 0;
      transform-origin: center;
      will-change: transform;
      z-index: 5;
      cursor: pointer;

      &:hover,
      &.active {
        color: white;
      }

      &:hover {
        font-size: 14px;
      }
    }
  }
}
</style>
