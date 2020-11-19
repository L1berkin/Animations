<template>
  <div class="container" @click="draw" @mousedown="startDraw" @mouseup="endDraw">

  </div>
</template>

<script>
export default {
  data() {
    return {
      container: ''
    }
  },
  mounted() {
    this.container = document.querySelector('.container')
  },
  methods: {
    draw() {
      const bubble = document.createElement('span')
      bubble.classList.add('bubble')
      const x = event.offsetX
      const y = event.offsetY
      const size = Math.random() * 100
      const duration = Math.random() * 10
      const timeLive = Math.random() * 4000

      this.css(bubble, {
        left: x + 'px',
        top: y + 'px',
        width: 20 + size + 'px',
        height: 20 + size + 'px',
        pointerEvents: 'none',
        marginLeft: -size / 2 + 'px',
        marginTop: -size / 2 + 'px',
        animation: `bubbles ${duration < 2 ? 3 : duration}s linear forwards`
      })

      setTimeout(() => {
        bubble.remove()
      }, timeLive)

      this.container.append(bubble)
    },
    startDraw() {
      this.container.addEventListener('mousemove', this.draw)
    },
    endDraw() {
      this.container.removeEventListener('mousemove', this.draw)
    },
    css($el, propertys = {}) {
      Object.keys(propertys).forEach(property => {
        $el.style[property] = propertys[property]
      })
    },
  }
}
</script>

<style lang="scss" scoped>
.container {
  overflow: hidden;
  position: relative;
  background: url(~@/assets/images/under-water.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
</style>
