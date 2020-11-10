<template>
  <div class="container">
    <div class="box">
      <div class="box__body">
        <span class="box__item"></span>
        <span class="box__item"></span>
        <span class="box__item"></span>
        <span class="box__item"></span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .container {
    background-color: #5f7d8b;
  }

  .box {
    position: absolute;
    top: calc(50% - 150px);
    left: calc(50% - 100px);
    transform: perspective(1000px) rotateY(-45deg);
    width: 200px;
    height: 300px;
    transform-style: preserve-3d;
    border-radius: 20px;
    &:before {
      content: '';
      position: absolute;
      bottom: -100px;
      left: 0;
      width: 100%;
      height: 50px;
      background-color: #000;
      filter: blur(40px);
      opacity: .5;
      transform: rotateX(90deg);
    }

    &__body {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      animation: rotate 5s linear infinite;
    }

    &__item {
      position: absolute;
      top: 0;
      left: 0;
      display: block;
      width: 100%;
      height: 100%;
      background: linear-gradient(0deg, #f1f1f1, #bbb, #f1f1f1);
      border-radius: 20px;
      &:nth-child(1) {
        transform: rotateX(0deg);
      }
      &:nth-child(2) {
        transform: rotateX(45deg);
      }
      &:nth-child(3) {
        transform: rotateX(-45deg);
      }
      &:nth-child(4) {
        transform: rotateX(90deg);
      }
    }
  }

  @keyframes rotate {
    0% {
    transform: perspective(1000px) rotateX(0deg);
    }
    100% {
    transform: perspective(1000px) rotateX(359deg);
    }
  }
</style>
