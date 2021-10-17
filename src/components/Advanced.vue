<template>
  <div class="advanced">
    <h2>Advanced Statistics</h2>
    <p>Track how your links are performing across the web with our advanced statistics dashboard.</p>
    <div class="sections container">
      <section class="section section--brand">
        <img src="../assets/icon-brand-recognition.svg" alt="Brand Recognition" />
        <h3>Brand Recognition</h3>
        <p>Boost your brand recognition with each click. Generic links don’t mean a thing. Branded links help instil confidence in your content.</p></section>
      <section class="section section--detailed">
        <img src="../assets/icon-detailed-records.svg" alt="Detailed Records"/>
        <h3>Detailed Records</h3>
        <p>Gain insights into who is clicking your links. Knowing when and where people engage with your content helps inform better decisions.</p></section>
      <section class="section section--customizable">
        <img src="../assets/icon-fully-customizable.svg" alt="Fully Customizable"/>
        <h3>Fully Customizable</h3>
        <p>Improve brand awareness and content discoverability through customizable links, supercharging audience engagement.</p></section>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Advanced'
}
</script>

<style lang="scss" scoped>
@use '../scss/utils' as *;

.advanced {
  padding-top: rem(60);
  text-align: center;
  background: var(--light-gray);
  position: relative;

  & p {
    color: var(--gray);
    margin-bottom: rem(80);
  }

  .sections {
    display: flex;
    flex-direction: row;
    gap: rem(30);

    &::before {
      content: "";
      position: absolute;
      display: block;
      height: rem(10);
      bottom: 30%;
      width: rem(900);
      background: var(--cyan);
    }

    & .section {
      position: relative;
      background: var(--white);
      border-radius: 1rem;
      padding: rem(40) 1rem 1rem;
      text-align: initial;
      flex: 1;
      font-size: rem(16);
      margin-bottom: 8rem;

      &--detailed {
        transform: translateY(15%);
      }
      &--customizable {
        transform: translateY(30%);
      }

      & p {
        margin-bottom: 1rem;
      }

      & img {
        position:absolute;
        top: 0;
        transform: translateY(-50%);
        left: rem(10);
        padding: 1rem;
        border-radius: 50%;
        background: var(--dark-violet);
      }
    }

  }
}

</style>
