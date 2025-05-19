<template>
  <div ref="wrapper" class="fade-in-wrapper">
    <slot />
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";

const wrapper = ref<HTMLElement | null>(null);

onMounted(() => {
  if (wrapper.value) {
    gsap.from(wrapper.value.children, {
      opacity: 0,
      y: -30,
      duration: 1,
      ease: "power2.out",
      stagger: 0.2,
    });
  }
});
</script>

<style scoped>
.fade-in-wrapper {
  display: contents; /* allows slot layout to flow naturally */
}
</style>
