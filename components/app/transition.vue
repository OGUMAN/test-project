<template>
  <div
    v-if="visible"
    class="transition-square"
    :class="animationState"
    @animationend="handleAnimationEnd"
  />
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const visible = ref(false);
const animationState = ref("");

const router = useRouter();

let nextRoute = null;
let navigationNext = null;

router.beforeEach((to, from, next) => {
  if (visible.value) {
    return; // Prevent multiple navigations
  }

  visible.value = true;
  animationState.value = "";
  nextRoute = to;
  navigationNext = next;

  // Start entering animation on next frame
  requestAnimationFrame(() => {
    animationState.value = "entering";
  });
});

function handleAnimationEnd(event) {
  if (event.animationName.includes("enter")) {
    // Entering animation done – now navigate
    if (navigationNext) {
      navigationNext(); // Proceed to route
      navigationNext = null;
    }

    // After slight delay, begin exit animation
    setTimeout(() => {
      animationState.value = "exiting";
    }, 50); // Adjust timing if needed
  } else if (event.animationName.includes("exit")) {
    // Exit animation complete – hide the square
    visible.value = false;
    animationState.value = "";
  }
}
</script>

<style scoped>
.transition-square {
  position: fixed;
  top: 50%;
  left: 50%;
  width: 150vw;
  height: 150vh;
  background: #ffcb46;
  transform: translate(-50%, -50%);
  z-index: 9999;
  pointer-events: none;
}

/* Animations */
@keyframes enter {
  from {
    transform: translate(-150%, -50%) rotate(-10deg);
  }
  to {
    transform: translate(-50%, -50%) rotate(0deg);
  }
}

@keyframes exit {
  from {
    transform: translate(-50%, -50%) rotate(0deg);
  }
  to {
    transform: translate(150%, -50%) rotate(10deg);
  }
}

.entering {
  animation: enter 0.6s ease-in-out forwards;
}

.exiting {
  animation: exit 0.6s ease-in-out forwards;
}
</style>
