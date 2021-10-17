<template>
    <div class="shorten container">
        <input type="text" name="" id="" placeholder="Shorten a link here...">
        <button class="button">Shorten It!</button>
    </div>
</template>

<script>

export default {
  name: 'Shorten'
}
</script>

<style lang="scss" scoped>
@use '../scss/utils' as *;
@use '../scss/style.scss';

.shorten {
  transform: translateY(50%);
  display: flex;
  justify-content: center;
  gap: 1rem;
  background: var(--dark-violet) url('../assets/bg-shorten-desktop.svg');
  border-radius: .5rem;
  padding: 2.5rem;
  position: relative;
  z-index: 2;

  & input {
    padding: 1rem;
    flex: 1;
    border-radius: .5rem;
  }

  & button {
    border-radius: .5rem;
    border: none;
    font-weight: 700;
  }
}

</style>
