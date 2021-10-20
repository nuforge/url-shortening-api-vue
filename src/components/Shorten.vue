<template>
  <div class="container">
    <form @submit.prevent="shortenLink">
      <div class="shorten">
        <div class="elements">
          <input type="text" name="shorten" id="shorten" placeholder="Shorten a link here..." v-model="link">
          <button class="button" >Shorten It!</button>
        </div>
        <div class="error" v-if="error"><br/>{{errorMsg}}</div>
      </div>
    </form>
  </div>
  <div class="results">
    <div class="container">
      <Result v-for="(result, index) in shortened" :key="index" v-bind:resultItem="result"/>
      <button @click="clearResults" class="button button--clear" v-if="shortened.length > 0">Clear Results</button>
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
  created () {
    const shortened = localStorage.getItem('shortenedUrls')
    console.log(shortened)
    if (shortened !== null) {
      this.shortened = JSON.parse(shortened)
    } else {
      localStorage.setItem('shortenedUrls', null)
    }
  },
  data () {
    return {
      link: null,
      shortened: [],
      error: false,
      errorMsg: null
    }
  },
  methods: {
    shortenLink () {
      this.error = false
      this.errorMsg = null
      fetch('https://api.shrtco.de/v2/shorten?url=' + this.link)
        .then(response => response.json())
        .then(data => {
          if (!data.ok) {
            console.log(data)
            this.error = true
            this.errorMsg = data.error
            return
          }
          this.shortened.push({
            original: data.result.original_link,
            shortened: data.result.full_short_link
          })
          this.storeResults()
        })
    },
    clearResults () {
      this.shortened = []
      localStorage.setItem('shortenedUrls', JSON.stringify(this.shortened))
    },
    storeResults () {
      localStorage.setItem('shortenedUrls', JSON.stringify(this.shortened))
    }
  }
}
</script>

<style lang="scss" scoped>
@use '../scss/utils' as *;
@use '../scss/style.scss';

.shorten {
  transform: translateY(50%);
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

.elements{
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.error {
  font-size: rem(12);
  color: red;
  display: block;
  font-weight: 500;
}

.results {
  background: var(--light-gray);
  padding-top: rem(80);
}

.button--clear {
  margin-top: 1rem;
}

</style>
