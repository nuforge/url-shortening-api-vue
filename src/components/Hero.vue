<template>
    <div class="container hero">
    <img alt="Illustration" src="@/assets/illustration-working.svg" class="illustration">
    <h1>More than just shorter links</h1>
    <p>Build your brand’s recognition and get detailed insights on how your links are performing.</P>
    <a class="button button--get-started">Get Started</a>
  </div>
</template>

<style lang="scss" scoped>
@use '../scss/utils' as *;

.hero {
  color: var(--grayish-Violet);
  position: relative;
  @include breakpoint(large) {
  padding: 2rem 25% 15rem 0;
    text-align: left;
  }

  & p {
    margin-bottom: 2rem;
  }
}

.illustration {
  @include breakpoint(large) {
    transform: translateX(26%);
    position: absolute;
    right: 0;
    z-index: -1;
  }
}

h1 {
  font-size: rem(56);
  line-height: 1.1;
  color: var(--dark-violet);
  margin-top: 0;
}
</style>
