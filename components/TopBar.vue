<template lang="pug">
.top-bar
  .container: .row
    .logo
      .logo__symbol
        img(src="~assets/logo-symbol.png")
      .logo__text
        .logo__name Digital Banking
        .logo__descr Be Safe Banking
    nav.menu
      a(class="menu__link" href="#") Cards
      a(class="menu__link" href="#") Service
      a(class="menu__link" href="#") Banking
      a(class="menu__link" href="#") FAQ
      a(class="menu__link" href="#") Contact
      a(class="menu__btn btn btn--roundSmall btn--small" href="#" role="button") Create Account
</template>
<script>
export default {
}
</script>

<style lang="scss">
.top-bar {
  background: linear-gradient(to top, rgba(#071d68, .1), rgba(#0b4bec, .1));
  padding: 20px 0 15px;

  .row {
    justify-content: space-between;
  }
  @media (min-width: 1200px) {
    padding: 40px 0 30px;
  }
}
.logo {
  color: white;
  display: flex;
  width: 100%;
  justify-content: center;

  @media (min-width: 992px) {
    flex: 0 0 calc(100% / 12 * 4);
    max-width: calc(100% / 12 * 4);
    justify-content: flex-start;
  }
}
.logo__text {
  margin-left: 15px;
}
.logo__name {
  font-size: 18px;
  font-family: "Poppins", sans-serif;
  font-weight: 600;
  text-transform: uppercase;
  line-height: 1.444;
  text-shadow: 0px 3px 3px rgba(30, 28, 28, .75);
  letter-spacing: -0.01em;
  position: relative;
  top: 7px;
}
.logo__descr {
  font-size: 12px;
  font-family: "Poppins", sans-serif;
  font-weight: 300;
  line-height: 2.167;
  letter-spacing: 0.25em;
}

.menu {
  font-size: 14px;
  font-family: "Poppins", sans-serif;
  font-weight: 600;
  text-transform: uppercase;
  line-height: 1.857;
  width: 100%;
  padding: 0 15px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  margin-top: 30px;

  @media (min-width: 576px) {
    margin-top: 15px;
    align-items: center;
  }
  @media (min-width: 992px) {
    flex: 0 0 calc(100% / 12 * 7);
    max-width: calc(100% / 12 * 7);
    flex-wrap: nowrap;
    transform: translateY(-7px);
    padding: 0 0 0 15px;
  }
}

.menu__link {
  color: white;
  text-decoration: none;
  transition: opacity .15s ease-in-out;

  &:hover {
    opacity: .7;
  }
}
.menu__btn {
  margin-left: auto;
  margin-right: auto;
  margin-top: 30px;

  @media (min-width: 576px) {
    margin: 0;
  }
}

</style>
