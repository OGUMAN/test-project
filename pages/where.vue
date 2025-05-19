<template>
  <BaseFadeIn>
    <section class="content container">
      <BaseMouseTilt>
        <h1>{{ $t("navigation.where") }}</h1>
      </BaseMouseTilt>
      <BaseContentAndImage>
        <template #content>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum.
          </p>
          <p>
            At vero eos et accusamus et iusto odio dignissimos ducimus qui
            blanditiis praesentium voluptatum deleniti atque corrupti quos
            dolores et quas molestias excepturi sint occaecati cupiditate non
            provident, similique sunt in culpa qui officia deserunt mollitia
            animi, id est laborum et dolorum fuga.
          </p>
          <BaseGoHome />
        </template>
        <template #image>
          <img src="~/assets/images/event2.webp" alt="Event 2" />
        </template>
      </BaseContentAndImage></section
  ></BaseFadeIn>
</template>
