<template>
  <div class="container">
    <div class="default-bg"></div>
    <section class="columns">
      <div class="column one"
        v-on:mouseenter="addClass"
        v-on:mouseleave="removeClass"
      >
        <div class="column__content">
          <h2 class="column__label">&lt; / &gt;</h2>
          <div class="column__box" :class="this.firstClass">
            <h3 class="column__title">HTML and CSS</h3>
            <p class="column__text">
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eos
              soluta omnis aliquam quas labore, earum magni ratione blanditiis
              iure accusantium porro natus recusandae et laborum itaque mollitia
              fuga ad quo.
            </p>
          </div>
        </div>
        <div class="bg bg-1" :class="this.firstClass"></div>
      </div>
      <div class="column two"
        v-on:mouseenter="addClass"
        v-on:mouseleave="removeClass"
      >
        <div class="column__content">
          <h2 class="column__label">Js</h2>
          <div class="column__box" :class="this.secondClass">
            <h3 class="column__title">Javascript</h3>
            <p class="column__text">
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eos
              soluta omnis aliquam quas labore, earum magni ratione blanditiis
              iure accusantium porro natus recusandae et laborum itaque mollitia
              fuga ad quo.
            </p>
          </div>
        </div>
        <div class="bg bg-2" :class="this.secondClass"></div>
      </div>
      <div class="column three"
        v-on:mouseenter="addClass"
        v-on:mouseleave="removeClass"
      >
        <div class="column__content">
          <h2 class="column__label">
            <img src="@/assets/images/react-label.png" alt="react" width="50%">
          </h2>
          <div class="column__box" :class="this.thirdClass">
            <h3 class="column__title">React</h3>
            <p class="column__text">
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eos
              soluta omnis aliquam quas labore, earum magni ratione blanditiis
              iure accusantium porro natus recusandae et laborum itaque mollitia
              fuga ad quo.
            </p>
          </div>
        </div>
        <div class="bg bg-3" :class="this.thirdClass"></div>
      </div>
      <div class="column four"
        v-on:mouseenter="addClass"
        v-on:mouseleave="removeClass"
      >
        <div class="column__content">
          <h2 class="column__label">
            <img src="@/assets/images/vue-label.png" alt="vue" width="50%">
          </h2>
          <div class="column__box" :class="this.fourthClass">
            <h3 class="column__title">Vue</h3>
            <p class="column__text">
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eos
              soluta omnis aliquam quas labore, earum magni ratione blanditiis
              iure accusantium porro natus recusandae et laborum itaque mollitia
              fuga ad quo.
            </p>
          </div>
        </div>
        <div class="bg bg-4" :class="this.fourthClass"></div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstClass: '',
      secondClass: '',
      thirdClass: '',
      fourthClass: ''
    }
  },
  methods: {
    addClass: function(event) {
      if (event.target.classList.contains('one')) {
        this.firstClass = 'active'
      } else if (event.target.classList.contains('two')) {
        this.secondClass = 'active'
      } else if (event.target.classList.contains('three')) {
        this.thirdClass = 'active' 
      } else {
        this.fourthClass = 'active'
      }
      
    },
    removeClass: function(event) {
      if (event.target.classList.contains('one')) {
        this.firstClass = ''
      } else if (event.target.classList.contains('two')) {
        this.secondClass = ''
      } else if (event.target.classList.contains('three')) {
        this.thirdClass = '' 
      } else {
        this.fourthClass = ''
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.default-bg {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-image: url('~@/assets/images/default.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  z-index: -2;
}

.columns {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.column {
  width: 25%;
  height: 100%;
  float: left;
  border-right: 2px solid rgba(0, 0, 0, 0.5);
  z-index: 1;
  &:last-child {
    border-right: none;
  }

  &__label {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 100%;
    text-align: center;
    color: #fff;
    opacity: 0.2;
    font-size: 8em;
  }

  &__content {
    position: relative;
    height: 100%;
  }

  &__box {
    position: absolute;
    top: 50%;
    transform: translateY(100%);
    padding: 40px;
    background-color: rgba(255, 255, 255, 1);
    text-align: center;
    transition: 0.5s;
    opacity: 0;
  }

  &__box.active {
    opacity: 1;
    transform: translateY(-50%);
  }

  &__title {
    font-size: 30px;
    color: #262626;
    font-weight: bold;
    padding-bottom: 0.5em;
  }

  &__text {
    color: #262626;
    font-size: 18px;
  }
}

.bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
  transition: 0.5s;
  opacity: 0.5;
  z-index: -1;
}

.active.bg {
  opacity: 1;
}

.active.bg-1 {
  background-image: url("~@/assets/images/logo_html-css.png");
}

.active.bg-2 {
  background-image: url("~@/assets/images/logo_js.png");
}

.active.bg-3 {
  background-image: url("~@/assets/images/logo_react.png");
}

.active.bg-4 {
  background-image: url("~@/assets/images/logo_vue.png");
}
</style>
