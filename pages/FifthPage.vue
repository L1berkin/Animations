<template>
  <div class="container">
    <section class="header">
      <nav class="header__nav">
        <ul class="main-nav">
          <router-link to="" class="main-nav__item"><li>Главная</li></router-link>
          <router-link to="" class="main-nav__item"><li>Главная</li></router-link>
          <router-link to="" class="main-nav__item"><li>Главная</li></router-link>
          <router-link to="" class="main-nav__item"><li>Главная</li></router-link>
          <router-link to="" class="main-nav__item"><li>Главная</li></router-link>          
        </ul>
      </nav>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.container {
  background-color: #ffffff;
}

.header {
  margin: 4em 0;
}

.main-nav {
  display: flex;
  justify-content: space-between;

  &__item {
    text-align: center;
    padding: 1em 0 0.5em;
    flex-grow: 1;
    &:after {
      content: '';
      display: block;
      width: 0%;
      margin: .5em auto 0;
      transition-duration: .5s;
      border-bottom: 2px solid black;
    }
    &:hover {
      &:after {
        width: 100%;
      }
    }
  }
}
</style>
