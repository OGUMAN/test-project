<template>
  <NuxtLink class="base-go-home" to="/">{{ $t("go-home") }}</NuxtLink>
</template>

<style lang="scss" scoped>
.base-go-home {
  text-decoration: none;
  color: black;
  padding: 12px 40px;
  display: block;
  width: fit-content;
  transition: color 0.2s, background-color 0.2s, transform 0.2s;
  font-family: "Roboto";
  font-size: 20px;
  border-radius: 10px;
  background-color: rgba(255, 255, 255, 0.45);
  color: black;

  &:hover {
    background-color: black;
    color: white;
    transform: scale(110%);
  }
}
</style>
