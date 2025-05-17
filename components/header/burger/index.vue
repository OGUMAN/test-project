<template>
  <div @click="toggleMenu" class="header-burger" :class="{ active: isMenuActive }"></div>
  <HeaderBurgerMenu v-if="isMenuActive" />
</template>

<script setup>
const isMenuActive = ref(false)
const toggleMenu = () => isMenuActive.value = !isMenuActive.value
const closeMenu = () => isMenuActive.value = false

provide('closeMenu', closeMenu)
</script>


<style lang="scss" scoped>
.header-burger {
  display: none;
  width: 22px;
  height: 22px;
  position: relative;
  cursor: pointer;
  transition: transform 0.3s ease;
  z-index: 10;

  @media screen and (max-width: 728px) {
    display: block;
  }

  &::before,
  &::after {
    content: "";
    position: absolute;
    left: 0;
    width: 100%;
    height: 2px;
    background: #000;
    transition: all 0.3s ease;
  }

  &::before {
    top: 6px;
  }

  &::after {
    bottom: 6px;
  }

  &.active::before {
    top: 10px;
    transform: rotate(45deg);
    background: white;
  }

  &.active::after {
    bottom: 10px;
    transform: rotate(-45deg);
    background: white;
  }
}
</style>
