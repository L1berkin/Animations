<template>
  <div class="container">
    <h1 class="title">Golden Autumn</h1>
    <section class="leaves">
      <div class="leaves__set">
      <div class="leaves__item"><img src="@/assets/images/leaf_2.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_1.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_3.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_4.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_2.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_1.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_3.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_4.png" alt=""></div>
    </div>
    <div class="leaves__set set-2">
      <div class="leaves__item"><img src="@/assets/images/leaf_2.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_1.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_3.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_4.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_2.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_1.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_3.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_4.png" alt=""></div>
    </div>
    <div class="leaves__set set-3">
      <div class="leaves__item"><img src="@/assets/images/leaf_2.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_1.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_3.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_4.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_2.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_1.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_3.png" alt=""></div>
      <div class="leaves__item"><img src="@/assets/images/leaf_4.png" alt=""></div>
    </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
  .container {
    background: radial-gradient(#333, #000);
  }

  .leaves {
    position: absolute;
    top: 0;
    width: 100%;
    height: 100vh;
    overflow: hidden;

    &__set {
      position: absolute;
      width: 100%;
      height: 100vh - $Header-height;
      top: 0;
      left: 0;
      z-index: 3;
    }

    &__item {
      position: absolute;
      display: block;
      pointer-events: none;
    }

    &__item:nth-child(1) {
      left: 20%;
      animation: animate 15s linear infinite;
      animation-delay: -7s;
    }
    &__item:nth-child(2) {
      left: 50%;
      animation: animate 20s linear infinite;
      animation-delay: -5s;
    }
    &__item:nth-child(3) {
      left: 70%;
      animation: animate 25s linear infinite;
    }
    &__item:nth-child(4) {
      left: 0%;
      animation: animate 15s linear infinite;
      animation-delay: -5s;
    }
    &__item:nth-child(5) {
      left: 85%;
      animation: animate 18s linear infinite;
      animation-delay: -10s;
    }
    &__item:nth-child(6) {
      left: 0%;
      animation: animate 12s linear infinite;
    }
    &__item:nth-child(7) {
      left: 15%;
      animation: animate 14s linear infinite;
    }
    &__item:nth-child(8) {
      left: 60%;
      animation: animate 15s linear infinite;
    }
  }

  .set-2 {
      transform: scale(2) rotateY(180deg);
      filter: blur(2px);
      z-index: 4;
  }

  .set-3 {
      transform: scale(0.8) rotateX(180deg);
      filter: blur(4px);
      z-index: 1;
  }

  .title {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 100%;
    text-align: center;
    color: #fff;
    font-size: 8em;
    z-index: 2;
  }

  @keyframes animate {
    0% {
      top: -10%;
      opacity: 0;
      transform: translateX(20px) rotate(0deg);
    }
    10% {
      opacity: 1;
    }
    20% {
      transform: translateX(-20px) rotate(45deg);
    }
    40% {
      transform: translateX(-20px) rotate(90deg);
    }
    60% {
      transform: translateX(20px) rotate(135deg);
    }
    80% {
      transform: translateX(-20px) rotate(180deg);
    }
    100% {
      top: 110%;
      transform: translateX(-20px) rotate(225deg);
    }
  }
</style>
