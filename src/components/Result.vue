<template>
    <div class="container">
        <div class="result">
            <div class="result__text result__text--original">{{resultItem.original}}</div>
            <div class="result__text result__text--shortened"><a :href="resultItem.shortened" target="_blank">{{resultItem.shortened}}</a></div>
            <div class="result__text result__text--copy ">
                <div :class="{button:true, copied: copied}" @click="copyToClipboard">
                    <div v-if="copied">Copied!</div>
                    <div v-else>Copy</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Result',
  props: ['resultItem'],
  data () {
    return {
      copied: false
    }
  },
  methods: {
    copyToClipboard () {
      navigator.clipboard.writeText(this.resultItem.shortened)
      this.copied = true
    }
  }
}
</script>

<style lang="scss" scoped>
@use '../scss/utils' as *;
@use '../scss/style.scss';
.container {
    margin-top: rem(50);
}
.result {
    display: flex;
    flex-direction: column;
    background: white;
    border-radius: rem(10);
    margin-top: 1rem;
    align-items: center;

    @include breakpoint(large) {
        flex-direction: row;
        justify-content: space-between;
    }

    &__text {
    padding: .5rem 1rem;
        @include breakpoint-down(large) {
            width: 100%;
        }
        &--original {
            @include breakpoint-down(large) {
                border-bottom: 1px solid var(--light-gray);
            }
        }
    }

    .button {
        border-radius: rem(8);
        &.copied {
            background: var(--dark-violet);
        }
    }
}

</style>
