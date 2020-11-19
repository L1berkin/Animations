<template>
  <div class="container">
    <div class="block-clock">
      <div class="clock">
        <span class="clock__number">1</span>
        <span class="clock__number">2</span>
        <span class="clock__number">3</span>
        <span class="clock__number">4</span>
        <span class="clock__number">5</span>
        <span class="clock__number">6</span>
        <span class="clock__number">7</span>
        <span class="clock__number">8</span>
        <span class="clock__number">9</span>
        <span class="clock__number">10</span>
        <span class="clock__number">11</span>
        <span class="clock__number">12</span>
        <div class="clock__arrows">
          <div class="arrows">
            <span class="arrows__arrow-hour"></span>
            <span class="arrows__center"></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="scss" scoped>
.container {
  background: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
}

.block-clock {
  width: 50%;
  min-height: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: -100px;
  border: 1px solid red;
}

.clock {
  width: 350px;
  height: 350px;
  position: relative;
  border: 1px solid blue;
  border-radius: 50%;
  font-weight: bold;
  font-size: 1.5em;
  background: radial-gradient(#fff, rgb(211, 218, 255));
  box-shadow: 0 0 5px 0 #000;

  &__number {
    position: absolute;
    &:nth-child(1) {
      top: 16%;
      right: 30%;
      transform: translate(50%, -50%);
    }
    &:nth-child(2) {
      top: 30%;
      right: 15%;
      transform: translate(50%, -50%);
    }
    &:nth-child(3) {
      top: 50%;
      right: 6%;
      transform: translate(-50%, -50%);
    }
    &:nth-child(4) {
      bottom: 30%;
      right: 15%;
      transform: translate(50%, 50%);
    }
    &:nth-child(5) {
      bottom: 16%;
      right: 30%;
      transform: translate(50%, 50%);
    }
    &:nth-child(6) {
      left: 50%;
      bottom: 5%;
      transform: translateX(-50%);
    }
    &:nth-child(7) {
      bottom: 16%;
      left: 30%;
      transform: translate(-50%, 50%);
    }
    &:nth-child(8) {
      bottom: 30%;
      left: 15%;
      transform: translate(-50%, 50%);
    }
    &:nth-child(9) {
      top: 50%;
      left: 6%;
      transform: translateY(-50%);
    }
    &:nth-child(10) {
      top: 30%;
      left: 15%;
      transform: translate(-50%, -50%);
    }
    &:nth-child(11) {
      top: 16%;
      left: 30%;
      transform: translate(-50%, -50%);
    }
    &:nth-child(12) {
      left: 50%;
      top: 6%;
      transform: translateX(-50%);
    }
  }

  &__arrows {
    position: absolute;
    width: 100%;
    height: 100%;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    border: 1px solid blue;
  }
}

.arrows {
  position: relative;
  width: 100%;
  height: 100%;

  &__center {
    position: absolute;
    width: 10px;
    height: 10px;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background: #ff4f4f;
    border-radius: 50%;
  }
  
  &__arrow-hour {
    position: absolute;
    left: 50%;
    bottom: 50%;
    width: 8px;
    height: 120px;
    border-radius: 10px;
    transform: translate(-50%, -10%);
    background:#ff4f4f;
  }
}
</style>
