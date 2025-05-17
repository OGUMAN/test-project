<template>
  <div class="base-content-image">
    <div class="base-content-image__content">
      <slot name="content" />
    </div>
    <div class="base-content-image__image">
      <slot name="image" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.base-content-image {
  width: 100%;
  display: flex;
  justify-content: space-between;
  gap: 30px;

  &__content {
    width: 100%;
  }

  &__image {
    max-width: 600px;
    width: 100%;
    height: 400px;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  @media screen and (max-width: 850px) {
    flex-direction: column-reverse;

    &__image {
      max-width: 100%;
    }
  }
}
</style>
