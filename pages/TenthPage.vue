<template>
  <div class="container" @mousemove="fly" @mousedown="fast" @mouseup="slow">
    <div ref="scene" class="scene">
      <div ref="rocket-box" class="rocket-box">
        <img src="@/assets/images/rocket.png" alt="ракета" class="rocket" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    const count = 30
    const scene = this.$refs.scene
    for (let i = 0; i < count; i++) {
      const star = this.createStar()
      scene.append(star)
    }
  },
  methods: {
    createStar() {
      const star = document.createElement('i')
      const x = Math.floor(Math.random() * window.innerWidth)

      const duration = Math.random() * 1
      const h = Math.random() * 100

      this.css(star, {
        left: x + 'px',
        width: 1 + 'px',
        height: 50 + h + 'px',
        position: 'absolute',
        top: '-250px',
        background: 'rgba(255, 255, 255, .5)',
        animation: `stars-10 ${duration}s linear infinite`,
        userSelect: 'none',
        pointerEvents: 'none'
      })
      return star
    },
    css($el, propertys = {}) {
      Object.keys(propertys).forEach(property => {
        $el.style[property] = propertys[property]
      })
    },
    fly(event) {
      const rocket = this.$refs['rocket-box']
      this.css(rocket, {
        left: event.offsetX + 'px',
        top: event.offsetY + 'px'
      })
    },
    fast() {
      this.$refs['rocket-box'].style.borderTop = '1px solid #fff'
      this.$refs.scene.querySelectorAll('i').forEach(star => {
        const duration = Math.random() * .1
        
        this.css(star, {
          animation: `stars-10 ${duration}s linear infinite`
        })
      })
    },
    slow() {
      this.$refs['rocket-box'].style.borderTop = null
      this.$refs.scene.querySelectorAll('i').forEach(star => {
        const duration = Math.random() * 1
        
        this.css(star, {
          animation: `stars-10 ${duration}s linear infinite`
        })
      })
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
  background: #01070a;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: none;

  &:active .rocket-box:before,
  &:active .rocket-box:after {
    background: linear-gradient(#ff12d7, transparent);
    bottom: -300px;
    height: 300px;
    filter: blur(2px);
  }
}

.rocket-box {
  position: absolute;
  pointer-events: none;
  animation: shaking 0.2s ease infinite;
  z-index: 1000;
  user-select: none;
  border-radius: 50%;
  &:before {
    content: '';
    position: absolute;
    top: 100%;
    left: 50%;
    transform: translateX(-50%);
    width: 10px;
    height: 200px;
    background: linear-gradient(#00d0ff, transparent);
  }
  &:after {
    content: '';
    position: absolute;
    top: 100%;
    left: 50%;
    transform: translateX(-50%);
    width: 10px;
    height: 200px;
    background: linear-gradient(#00d0ff, transparent);
    filter: blur(20px);
  }
}

@keyframes shaking {
  0%,
  100% {
    transform: translate(-50%, -52px);
  }
  50% {
    transform: translate(-50%, -48px);
  }
}
</style>
