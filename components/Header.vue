<template>
  <header class="header">
    <nav class="header__nav">
      <ul class="main-nav">
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">First</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Second</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Third</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Fourth</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Fifth</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Sixth</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Seventh</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Eighth</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Ninth</nuxt-link></li>
        <li class="main-nav__item"><nuxt-link to="" class="main-nav__link">Tenth</nuxt-link></li>
      </ul>
    </nav>
  </header>
</template>
<style lang="scss" scoped>
  .header {
    box-shadow: 0 0 5px;
    background-color: rgba(255, 255, 255, 0.4);
  }

  .main-nav {
    width: 100%;
    display: flex;
    align-items: center;

    &__item {
      width: 10%;
      text-align: center;
    }

    &__link {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 6vw;
      &:hover {
        background-color: rgba(204, 204, 204, 0.4);
      }
    }
  }
</style>