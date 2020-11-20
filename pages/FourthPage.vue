<template>
  <div class="container">
    <div class="clock">
      <div class="clock__hour">
        <div class="hr" id="hr"></div>
      </div>
      <div class="clock__min">
        <div class="mn" id="mn"></div>
      </div>
      <div class="clock__sec">
        <div class="sc" id="sc"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    const hr = document.querySelector('#hr')
    const mn = document.querySelector('#mn')
    const sc = document.querySelector('#sc')

    const deg = 6

    setInterval(() => {
      const day = new Date()
      const hh = day.getHours() * 30
      const mm = day.getMinutes() * deg
      const ss = day.getSeconds() * deg

      hr.style.transform = `rotateZ(${(hh)+(mm/12)})`
      mn.style.transform = `rotateZ(${mm}deg)`
      sc.style.transform = `rotateZ(${ss}deg)`
    }, 1000);

    
  }
}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: $Header-height;
  margin-top: -$Header-height;
  background: #091921;
}

.clock {
  width: 350px;
  height: 350px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: url(~@/assets/images/clock.png);
  background-size: cover;
  border: 4px solid #091921;
  border-radius: 50%;
  box-shadow: 0 -15px 15px rgba(255, 255, 255, .05),
              inset 0 -15px 15px rgba(255, 255, 255, .05),
              0 -15px 15px rgba(0, 0, 0, .03),
              inset 0 -15px 15px rgba(0, 0, 0, .03);

  &__hour, &__min, &__sec {
    position: absolute;
  }

  &__hour, .hr {
    width: 160px;
    height: 160px;
  }

  &__min, .mn {
    width: 190px;
    height: 190px;
  }

  &__sec, .sc {
    width: 230px;
    height: 230px;
  }
}

.clock::before {
  content: '';
  position: absolute;
  width: 15px;
  height: 15px;
  background: #fff;
  border-radius: 50%;
  z-index: 1000;
}

.hr, .mn, .sc {
  display: flex;
  justify-content: center;
  position: absolute;
  border-radius: 50%;
  &::before {
    content: '';
    position: absolute;
    border-radius: 50%;
    border-radius: 6px 6px 0 0;
  }
}

.hr::before {
  width: 8px;
  height: 80px;
  background: #ff105e;
  z-index: 10;
}

.mn::before {
  width: 4px;
  height: 90px;
  background: #fff;
  z-index: 11;
}

.sc::before {
  width: 2px;
  height: 150px;
  background: #fff;
  z-index: 12;
}
</style>
