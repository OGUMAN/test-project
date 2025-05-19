<template>
  <div class="menu">
    <BaseLink :path="'what'" @click="closeMenu">{{
      $t("navigation.what")
    }}</BaseLink>
    <BaseLink :path="'who'" @click="closeMenu">{{
      $t("navigation.who")
    }}</BaseLink>
    <BaseLink :path="'where'" @click="closeMenu">{{
      $t("navigation.where")
    }}</BaseLink>
  </div>
</template>

<script setup>
import { inject } from "vue";

const closeMenu = inject("closeMenu");
</script>

<style lang="scss" scoped>
.menu {
  position: fixed;
  inset: 0;
  z-index: 999;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  z-index: 9;

  background-color: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(6px);

  animation: fadeIn 0.3s ease;

  a {
    font-size: 30px;
    margin: 1rem 0;
    color: white;
    text-decoration: none;
    transition: opacity 0.2s, font-size .2s;
    opacity: 0.7;

    &:hover {
      opacity: 1;
      font-size: 35px;
    }
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
