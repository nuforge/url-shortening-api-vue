<template>
  <Header/>
  <router-view/>
  <Footer/>
</template>

<script>

import Header from './components/Header'
import Footer from './components/Footer'
export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
}
</script>

<style lang="scss">
@use './scss/utils' as *;
@use './scss/style.scss';

.brand {
  font-weight: 700;
  font-size: rem(28);
}

.button {
  background: var(--cyan);
  padding: .5rem 1rem;
  border-radius: 2rem;
  color: var(--white);
  cursor: pointer;
  outline: none;
  border: none;
}

</style>
