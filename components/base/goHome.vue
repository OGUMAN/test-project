<template>
  <NuxtLink class="base-go-home" to="/">{{ $t('go-home') }}</NuxtLink>
</template>

<style lang="scss" scoped>
.base-go-home {
  text-decoration: none;
  color: black;
  padding: 10px 20px;
  display: block;
  border: 1px solid black;
  width: fit-content;
  border-radius: 10px;
  transition: color .2s, background-color .2s, transform .2s;

  &:hover {
    background-color: black;
    color: white;
    transform: scale(115%);
  }
}
</style>
