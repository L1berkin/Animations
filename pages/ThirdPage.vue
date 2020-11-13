<template>
  <div class="container">
    <div class="card">
      <div class="card__body">
        <div class="card-front">
          <h1 class="title">FRONT</h1>
          <div class="logo"></div>
          <p class="content">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor qui
            quod hic quos explicabo facere rerum iste animi excepturi blanditiis
            eligendi sequi, deleniti voluptatem eum laudantium? Voluptates id
            obcaecati dolores?
          </p>
        </div>

        <div class="card-back">
          <h1 class="title">BACK</h1>
          <div class="logo"></div>
          <p class="content">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor qui
            quod hic quos explicabo facere rerum iste animi excepturi blanditiis
            eligendi sequi, deleniti voluptatem eum laudantium? Voluptates id
            obcaecati dolores?
          </p>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="card__body">
        <div class="card-front">
          <h1 class="title">FRONT</h1>
          <div class="logo"></div>
          <p class="content">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor qui
            quod hic quos explicabo facere rerum iste animi excepturi blanditiis
            eligendi sequi, deleniti voluptatem eum laudantium? Voluptates id
            obcaecati dolores?
          </p>
        </div>

        <div class="card-back">
          <h1 class="title">BACK</h1>
          <div class="logo"></div>
          <p class="content">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor qui
            quod hic quos explicabo facere rerum iste animi excepturi blanditiis
            eligendi sequi, deleniti voluptatem eum laudantium? Voluptates id
            obcaecati dolores?
          </p>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="card__body">
        <div class="card-front">
          <h1 class="title">FRONT</h1>
          <div class="logo"></div>
          <p class="content">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor qui
            quod hic quos explicabo facere rerum iste animi excepturi blanditiis
            eligendi sequi, deleniti voluptatem eum laudantium? Voluptates id
            obcaecati dolores?
          </p>
        </div>

        <div class="card-back">
          <h1 class="title">BACK</h1>
          <div class="logo"></div>
          <p class="content">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor qui
            quod hic quos explicabo facere rerum iste animi excepturi blanditiis
            eligendi sequi, deleniti voluptatem eum laudantium? Voluptates id
            obcaecati dolores?
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
$border-radius: 10px;

.container {
  display: flex;
  align-items: center;
  justify-content: space-around;
  background-image: url("~@/assets/images/backgrounds/road.jpg");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.card {
  width: 250px;
  height: 350px;
  margin-top: -$Header-height;
  border-radius: $border-radius;
  &:hover {
    .card__body {
      transform: perspective(400px) rotateX(-180deg);
    }

    .card-front {
      opacity: 0;
    }

    .card-back {
      opacity: 1;
    }
  }

  &__body {
    width: 100%;
    height: 100%;
    position: relative;
    transition-duration: 0.8s;
    transform: perspective(400px);
  }
}

.card-front {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  border-radius: $border-radius;
  background-color: #fff;
  transition-delay: 0.215s;
  box-shadow: 0 0 10px 0 #000;
}

.card-back {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  border-radius: $border-radius;
  background-color: #ccc;
  opacity: 0;
  transform: rotateX(180deg);
  transition-delay: 0.215s;
  transition-property: opacity;
  box-shadow: 0 0 10px 0 #000;
}

.title {
  margin: 1em 0;
}

.logo {
  width: 90px;
  height: 90px;
  border-radius: 50%;
  background-color: rgba(6, 111, 0, 0.306);
  margin: 0 auto 2em;
}

.content {
  margin: 0 .5em;
}
</style>
