<template>
  <div class="container">
    <div class="scene">
      <div id="moonSun" class="moonSun" v-on:click="newDay()">
        <img class="moon" src="@/assets/images/moon.png" alt="луна" width="100%">
      </div>
      <img src="@/assets/images/forest.png" alt="лес" class="forest" />
      <img src="@/assets/images/cloud1.png" alt="облако" class="cloud cloud1" />
      <img src="@/assets/images/cloud2.png" alt="облако" class="cloud cloud2" />
      <img src="@/assets/images/cloud3.png" alt="облако" class="cloud cloud3" />
      <img src="@/assets/images/cloud1.png" alt="облако" class="cloud cloud4" />
      <img src="@/assets/images/cloud2.png" alt="облако" class="cloud cloud5" />
      <img src="@/assets/images/cloud3.png" alt="облако" class="cloud cloud6" />
      <div class="island-box hide">
        <img src="@/assets/images/остров.png" alt="остров" class="island-box__img" width="100%">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stars: []
    }
  },
  mounted() {
    const count = 500
    const scene = document.querySelector('.scene')
    const box = document.createElement('div')
    for (let i = 0; i < count; i++) {
      const star = document.createElement('i')
      star.classList.add('star')
      const x = Math.floor(Math.random() * innerWidth)
      const y = Math.floor(Math.random() * innerHeight)
      const duration = Math.random() * 10
      const size = Math.random() * 2

      this.css(star, {
        left: x + 'px',
        top: y + 'px',
        width: 1 + size + 'px',
        height: 1 + size + 'px',
        position: 'absolute',
        background: '#fff',
        borderRadius: '100%',
        animation: 'stars-8 linear infinite',
        animationDuration: 5 + duration +'s',
        animationDelay: duration +'s'
      })

      this.stars.push(star)
      scene.append(star)
    }
    
    this.clouds = document.querySelectorAll('.cloud')
    this.moonSun = document.querySelector('#moonSun')
    this.forest = document.querySelector('.forest')
    this.moon = document.querySelector('.moon')
    this.bg = document.querySelector('.scene')
    this.island = document.querySelector('.island-box')
  },
  methods: {
    css($el, propertys = {}) {
      Object.keys(propertys).forEach(property => {
        $el.style[property] = propertys[property]
      })
    },
    newDay() {
      this.moonSun.classList.toggle('sun')
      this.moonSun.classList.toggle('moon')
      this.hideShow(this.forest)
      this.hideShow(this.moon)
      this.hideShow(this.island)
      if (!this.stars[1].style.display) {
        Object.keys(this.stars).forEach( count => {
        this.stars[count].style.display = 'none'
      })
      } else {
        Object.keys(this.stars).forEach( count => {
        this.stars[count].style.display = ''
      })
      }

      this.clouds.forEach(cloud => {
        this.hideShow(cloud)
      })

      this.stars.forEach(star => {
        this.hideShow(star)
      })

      this.changeBg(this.bg)
    },
    hideShow($el) {
      $el.classList.toggle('hide')
    },
    changeBg($el) {
      if (!$el.style.background) {
        $el.style.background = 'linear-gradient(#d85600, #ffc527)'
      } else {
        $el.style = ''
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.scene {
  position: relative;
  width: 100%;
  height: 100vh;
  margin-top: -$Header-height;
  background: linear-gradient(#111425, #3751e0);
  background-attachment: fixed;
  overflow: hidden;
}

.island-box {
  position: absolute;
  width: 70%;
  min-width: 700px;
  bottom: 0%;
  right: 10%;
  transition-duration: 1s;
}

.moonSun {
  position: absolute;
  top: 100px;
  left: 400px;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  z-index: 1000;
  cursor: pointer;
  transition-duration: 1s;
}

.moon {
  transition-duration: 1s;
}

.sun {
  position: absolute;
  top: 100px;
  left: 400px;
  width: 100px;
  height: 100px;
  background: rgb(255, 153, 0);
  border-radius: 50%;
  z-index: 1000;
  cursor: pointer;
  transition-duration: 1s;
  transform: translate(-100px, 50px) scale(1.5);
  &:before {
    content: '';
    display: block;
    position: absolute;
    left: -10px;
    top: -10px;
    width: 120px;
    height: 120px;
    border-radius: 50%;
    background: radial-gradient(rgb(255, 153, 0) ,rgba(255, 201, 120, 0.5));
  }
  &:after {
    content: '';
    display: block;
    position: absolute;
    left: -20px;
    top: -20px;
    width: 140px;
    height: 140px;
    border-radius: 50%;
    background: radial-gradient(rgb(255, 153, 0) ,rgba(255, 214, 152, 0.394));
    box-shadow: 0 0 60px 20px rgba(255, 186, 82, 0.7);
  }
}

.hide {
  opacity: 0;
}

.hide-star {
  display: none;
}

.forest {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  transition-duration: 1s;
  transition-property: opacity;
  transform: scale(1.2);
}

.cloud {
  position: absolute;
  left: 0;
  z-index: 1000;
  pointer-events: none;
  transition-duration: 1s;
}

.cloud1 {
  top: 0;
  max-width: 600px;
  animation: animateCloud 50s linear infinite;
}
.cloud2 {
  top: 0;
  max-width: 500px;
  animation: animateCloud 35s linear infinite;
}
.cloud3 {
  top: 0;
  max-width: 600px;
  animation: animateCloud 80s linear infinite;
}
.cloud4 {
  top: 200px;
  max-width: 300px;
  animation: animateCloud 70s linear infinite;
  animation-delay: -20s;
}
.cloud5 {
  top: 150px;
  max-width: 500px;
  animation: animateCloud 40s linear infinite;
  animation-delay: -5s;
}
.cloud6 {
  top: 75px;
  max-width: 400px;
  animation: animateCloud 30s linear infinite;
  animation-delay: -10s;
}

@keyframes animateCloud {
  0% {
    transform: translateX(-100%) scale(1);
  }
  100% {
    transform: translateX(400%) scale(1);
  }
}
</style>
