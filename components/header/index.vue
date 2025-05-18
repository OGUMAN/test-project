<template>
  <header class="header">
    <div class="header__container container content">
      <div class="header__item">
        <HeaderLanguage />
      </div>
      <div class="header__item">
        <BaseLogo />
      </div>
      <div class="header__item">
        <HeaderBurger />
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use "style";

.header {
  display: flex;
  justify-content: center;

  .header__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: style.$height;
    position: absolute;
    width: 100%;
    z-index: 8;
    padding-top: 0;
    padding-bottom: 0;
  }

  &__item {
    width: 33.33%;
    display: flex;
    justify-content: center;

    &:first-child {
      justify-content: flex-start;
    }

    &:last-child {
      justify-content: flex-end;
    }
  }
}
</style>
