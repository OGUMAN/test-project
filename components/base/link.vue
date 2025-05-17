<template>
  <NuxtLink class="base-link" :to="props.path"><slot /></NuxtLink>
</template>

<script lang="ts" setup>
const props = defineProps({
  path: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
.base-link {
  font-size: 16px;
  transition: color 0.3s;
  color: inherit;
  text-decoration: none;
  position: relative;

  &:hover {
    color: white;
  }

  &:after {
    content: "";
    position: absolute;
    top: calc(100% + 2px);
    left: 0;

    width: 100%;
    height: 2px;
    background: white;

    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s ease;
  }

  &:hover:after {
    transform: scaleX(1);
  }
}

</style>
