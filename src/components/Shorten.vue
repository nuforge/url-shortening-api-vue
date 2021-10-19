<template>
  <div class="container">
      <form @submit.prevent="shortenLink">
    <div class="shorten">
        <input type="text" name="" id="" placeholder="Shorten a link here..." v-model="link">
        <button class="button" >Shorten It!</button>
    </div>
      </form>
  </div>
  <div class="results">
    <div class="container">
      <Result v-for="(result, index) in shortened" :key="index" v-bind:resultItem="result"/>
    </div>
  </div>
</template>

<script>
import Result from '@/components/Result'

export default {
  name: 'Shorten',
  components: {
    Result
  },
  data () {
    return {
      link: null,
      shortened: []
    }
  },
  methods: {
    shortenLink () {
      fetch('https://api.shrtco.de/v2/shorten?url=' + this.link)
        .then(response => response.json())
        .then(data => {
          this.shortened.push({
            original: data.result.original_link,
            shortened: data.result.full_short_link
          })
        })
    }
  }
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
  background: var(--dark-violet) url('../assets/bg-shorten-mobile.svg');
  background-size: cover;
  border-radius: .5rem;
  padding: 2.5rem;
  position: relative;
  z-index: 2;
    @include breakpoint(large) {
      background: var(--dark-violet) url('../assets/bg-shorten-desktop.svg');

    }

  & input {
    padding: 1rem;
    flex: 1;
    border-radius: .5rem;
    outline: none;
  }

  & button {
    border-radius: .5rem;
    border: none;
    font-weight: 700;
  }
}

.results {
  background: var(--light-gray);
  padding-top: rem(80);
}

</style>
