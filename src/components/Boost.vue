<template>
    <div class="boost">
    <h2>Boost your links today</h2>

    <a class="button">Get Started</a></div>
</template>

<script>

export default {
  name: 'Boost'
}
</script>

<style lang="scss" scoped>
@use '../scss/utils' as *;

.boost {
  text-align: center;
  background: var(--dark-violet) url('../assets/bg-boost-mobile.svg');
  background-size: cover;
  padding: 3rem;
  color: var(--white);

  @include breakpoint(large){
    background: var(--dark-violet) url('../assets/bg-boost-desktop.svg');
    background-size: cover;
  }
}

</style>
