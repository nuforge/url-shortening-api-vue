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
  text-align: left;
  padding: 2rem 30% 15rem 0;
  color: var(--grayish-Violet);

  & p {
    margin-bottom: 2rem;
  }
}

.illustration {
  position: absolute;
  right: 0;
  transform: translateX(-10%);
  z-index: -1
}

h1 {
  font-size: rem(56);
  line-height: 1.1;
  color: var(--dark-violet);
}
</style>
