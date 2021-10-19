<template>
    <header class="header container">
    <img src="@/assets/logo.svg" class="logo" />
    <nav :class="{nav: true, showNav: showNav}">
      <router-link to="#" class="nav__link">Features</router-link>
      <router-link to="#" class="nav__link">Pricing</router-link>
      <router-link to="#" class="nav__link nav__link--resources">Resources</router-link>
      <router-link to="#" class="nav__link nav__link--login">Login</router-link>
      <router-link to="#" class="nav__link nav__link--signup button">Sign Up</router-link>
    </nav>
    <div class="menu" @click="toggleNav"></div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      showNav: false
    }
  },
  methods: {
    toggleNav () {
      this.showNav = !this.showNav
    }
  }
}
</script>
<style lang="scss" scoped>
@use '../scss/utils' as *;
@use '../scss/style.scss';

.header {
    display: flex;
    align-items: center;
    padding: rem(30) 0;
    justify-content: space-between;
}

.nav {
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 1rem;
  padding: 1rem;

  @include breakpoint-down(large) {
    max-width: rem(375);
    position: absolute;
    top: rem(80);
    z-index: 2;
    background: var(--dark-violet);
    left: 50%;
    transform: translateX(-50%);
    width: 90%;
    border-radius: 1rem;

    &:not(.showNav) {
      transform: translateX(-10000px);
    }
  }

  @include breakpoint(large) {
    flex-direction: row;
  }

  &__link {
    flex: 1;
    justify-items: end;
    text-decoration: none;
    font-size: rem(14);
    font-weight: bold;
    color: var(--gray);
    text-align: center;
        width: 100%;
    &--login {
      flex: 4;
      @include breakpoint(large) {
      text-align: right;
      }
    }
    &--resources {
      @include breakpoint-down(large) {
        padding-bottom: 1rem;
        border-bottom: 1px solid var(--gray);
      }
    }

    &.button {
      color: var(--white);
    }
  }
}

.menu {
  width: 35px;
  height: 5px;
  background: black;
  cursor: pointer;

  @include breakpoint(large) {
    display: none;
  }

  &::before {
    content: "";
    display: block;
    width: 35px;
    height: 5px;
    background: black;
    position: relative;
    top: -10px;
  }
  &::after {
    content: "";
    display: block;
    width: 35px;
    height: 5px;
    background: black;
    position: relative;
    top: 5px;
  }
}
</style>
