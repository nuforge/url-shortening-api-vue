<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__links footer__links--brand">
        <img src="@/assets/logo-white.svg" class="logo"/>
      </div>
      <div class="footer__links footer__links--features">
        Features
        <ul>
          <li>Link Shortening</li>
          <li>Branded Links</li>
          <li>Analytics</li>
        </ul>
      </div>
      <div class="footer__links footer__links--resources">
        Resources
        <ul>
          <li>Blog</li>
          <li>Developers</li>
          <li>Support</li>
        </ul>
        </div>
      <div class="footer__links footer__links--company">
        Company
        <ul>
          <li>About</li>
          <li>Our Team</li>
          <li>Careers</li>
          <li>Contact</li>
        </ul></div>
      <div class="footer__links footer__links--social">
        <a><img src="@/assets/icon-facebook.svg"/></a>
        <a><img src="@/assets/icon-twitter.svg"/></a>
        <a><img src="@/assets/icon-pinterest.svg"/></a>
        <a><img src="@/assets/icon-instagram.svg"/></a>
      </div>
    </div>
</footer>
</template>

<script>

export default {
  name: 'Footer'
}
</script>

<style lang="scss" scoped>
@use '../scss/utils' as *;

.logo {
  fill: white;
}
.footer {
  background: var(--very-dark-violet);
  color: white;
  padding: 3rem;

  &__links {
    flex: 1;
    font-size: rem(16);
    font-weight: 500;

    &--brand {
      flex: 2;
    }
    &--social {
      display: flex;
      gap: 1rem;
    }
  }

  & .container {
    display: flex;
  }

  &__links ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }

}

</style>
