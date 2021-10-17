<template>
    <header class="header container">
    <div class="brand">
      <router-link to="/" class="nav__link"><img src="@/assets/logo.svg" class="logo"/></router-link></div>
    <nav class="nav">
      <router-link to="/about" class="nav__link">Features</router-link>
      <router-link to="/about" class="nav__link">Pricing</router-link>
      <router-link to="/about" class="nav__link" >Resources</router-link>
      <router-link to="/about" class="nav__link nav__link--login">Login</router-link>
      <router-link to="/about" class="nav__link nav__link--signup button">Sign Up</router-link>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
@use '../scss/utils' as *;
@use '../scss/style.scss';

.header {
    display: flex;
    align-items: center;
}

.nav {
  width: 100%;
  padding: rem(30);
  display: flex;
  align-items: center;
  gap: 1rem;

  &__link {
    flex: 1;
    justify-items: end;
    text-decoration: none;
    font-weight: bold;
    color: var(--gray);
    text-align: center;
    &--login {
      flex: 2;
      text-align: right;
    }

    &.button {
      color: var(--white);
    }
  }
}
</style>
