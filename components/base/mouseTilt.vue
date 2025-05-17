<template>
    <div ref="container" class="tilt-container">
      <slot />
    </div>
  </template>
<script setup>
import { gsap } from "gsap";

const container = ref(null);
let animation = null;

const handleMouseMove = (e) => {
  const { innerWidth, innerHeight } = window;
  const x = (e.clientX - innerWidth / 2) / 40;
  const y = (e.clientY - innerHeight / 2) / 40;

  animation?.kill();
  animation = gsap.to(container.value, {
    x,
    y,
    duration: 0.4,
    ease: "power3.out",
  });
};

onMounted(() => {
  window.addEventListener("mousemove", handleMouseMove);
});

onBeforeUnmount(() => {
  window.removeEventListener("mousemove", handleMouseMove);
  animation?.kill();
});
</script>

<style scoped>
.tilt-container {
  display: inline-block;
  will-change: transform;
}
</style>