<template>
  <BaseContentAndImage class="content container">
    <template #content>
      <BaseMouseTilt>
        <h1>{{ $t("navigation.where") }}</h1>
      </BaseMouseTilt>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
        veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
        commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
        velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
        occaecat cupidatat non proident, sunt in culpa qui officia deserunt
        mollit anim id est laborum.
      </p>
      <BaseGoHome />
    </template>
    <template #image>
      <img src="~/assets/images/event2.webp" alt="Event 2" />
    </template>
  </BaseContentAndImage>
</template>
