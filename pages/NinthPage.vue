<template>
  <div class="container" @mousemove="parallax">
    <section class="box">
      <img src="@/assets/images/Geom/1.png" data-speed="-5" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/2.png" data-speed="5" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/3.png" data-speed="2" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/4.png" data-speed="6" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/5.png" data-speed="8" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/6.png" data-speed="-2" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/7.png" data-speed="4" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/8.png" data-speed="-9" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/9.png" data-speed="6" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/10.png" data-speed="-7" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/11.png" data-speed="-5" alt="" class="geom-img layer">
      <img src="@/assets/images/Geom/12.png" data-speed="5" alt="" class="geom-img layer">
      <h2 class="layer" data-speed="2">Parallax</h2>
    </section>
  </div>
</template>

<script>
export default {
  methods: {
    parallax(event) {
      document.querySelectorAll('.layer').forEach(layer => {
        const speed = layer.getAttribute('data-speed')

        const x = (window.innerWidth - event.pageX*speed)/100
        const y = (window.innerHeight - event.pageY*speed)/100

        layer.style.transform = `translate(${x}px, ${y}px)`
      })
    }
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: #111;
  }

  .box {
    position: relative;
    width: 100%;
    height: 100vh;
    margin-top:  -$Header-height;
    overflow: hidden;
    display: flex;justify-content: center;
    align-items: center;
  }

  .layer {
    position: relative;
    color: #fff;
    font-size: 10em;
    pointer-events: none;
    user-select: none;
  }

  .geom-img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

</style>
