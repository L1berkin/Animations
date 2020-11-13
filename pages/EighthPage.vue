<template>
  <div class="container">
    <div class="scene">
      <div class="moon"></div>
      <img src="@/assets/images/forest.png" alt="Лес" class="forest" />
      <img src="@/assets/images/cloud1.png" alt="Лес" class="cloud cloud1" />
      <img src="@/assets/images/cloud2.png" alt="Лес" class="cloud cloud2" />
      <img src="@/assets/images/cloud3.png" alt="Лес" class="cloud cloud3" />
      <img src="@/assets/images/cloud1.png" alt="Лес" class="cloud cloud4" />
      <img src="@/assets/images/cloud2.png" alt="Лес" class="cloud cloud5" />
      <img src="@/assets/images/cloud3.png" alt="Лес" class="cloud cloud6" />

    </div>
  </div>
</template>

<script>
export default {
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
        borderRadius: '50%',
        animation: 'stars linear infinite',
        animationDuration: 5 + duration +'s',
        animationDelay: duration +'s'

      })

      scene.append(star)
    }

  },
  methods: {
    css($el, propertys = {}) {
      Object.keys(propertys).forEach(property => {
        $el.style[property] = propertys[property]
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  background-color: #9f9f9f;
}

.scene {
  position: relative;
  width: 100%;
  height: 100vh;
  margin-top: -$Header-height;
  background: linear-gradient(#111425, #3751e0);
  background-attachment: fixed;
  overflow: hidden;
}

.moon {
  position: absolute;
  top: 100px;
  left: 400px;
  width: 100px;
  height: 100px;
  background: #fff;
  border-radius: 50%;
  z-index: 1000;
  cursor: pointer;
  &:after {
    content: "";
    position: absolute;
    top: -15px;
    left: 15px;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: linear-gradient(#111425, #3751e0);
    background-attachment: fixed;
  }
}

.forest {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  transform: scale(1.2);
}

.cloud {
  position: absolute;
  left: 0;
  z-index: 1000;
  pointer-events: none;
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
