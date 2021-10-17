<template>
  <Hero />
  <Shorten />
  <Advanced />
  <Boost />
</template>

<script>
// @ is an alias to /src
import Hero from '@/components/Hero'
import Shorten from '@/components/Shorten'
import Advanced from '@/components/Advanced'
import Boost from '@/components/Boost'

export default {
  name: 'Home',
  components: {
    Hero,
    Shorten,
    Advanced,
    Boost
  }
}
</script>

<style lang="scss" scoped>
@use '../scss/utils' as *;

</style>
