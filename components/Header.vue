<template>
  <header class="header">
    <nav class="header__nav">
      <ul class="main-nav">
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'index'}" no-prefetch  exact active-class="active" class="main-nav__link">
            First
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'SecondPage'}" no-prefetch active-class="active" class="main-nav__link">
            Second
          </nuxt-link></li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'ThirdPage'}" no-prefetch active-class="active" class="main-nav__link">
            Third
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'FourthPage'}" no-prefetch active-class="active" class="main-nav__link">
            Fourth
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'FifthPage'}" no-prefetch active-class="active" class="main-nav__link">
            Fifth
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'SixthPage'}" no-prefetch active-class="active" class="main-nav__link">
            Sixth
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'SeventhPage'}" no-prefetch active-class="active" class="main-nav__link">
            Seventh
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'EighthPage'}" no-prefetch active-class="active" class="main-nav__link">
            Eighth
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'NinthPage'}" no-prefetch active-class="active" class="main-nav__link">
            Ninth
          </nuxt-link>
        </li>
        <li class="main-nav__item">
          <nuxt-link :to="{ name: 'TenthPage'}" no-prefetch active-class="active" class="main-nav__link">
            Tenth
          </nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>
<style lang="scss" scoped>
  .header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    box-shadow: 0 0 5px;
    background-color: rgba(255, 255, 255, 0.231);
    z-index: 10;
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
      height: $Header-height;
      color: rgba(0, 0, 0, 0.877);
      transition-duration: .5s;
      user-select: none;
      &:hover {
        background-color: rgba(175, 175, 175, 0.53);
        box-shadow: 0 0 10px 0 #fff;
        color: #fff;
      }
      &:active {
        background-color: rgba(255, 255, 255, 0.53);
        color: rgb(128, 128, 128);
      }
    }
  }

  .active {
    background-color: rgba(175, 175, 175, 0.51);
  }
</style>