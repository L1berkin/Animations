<template>
  <div class="container">
    <ul class="links-list">
      <li class="links-list__item">
        <a href="" class="links-list__link">
          <img
            src="@/assets/images/social/facebook_icon.svg"
            alt="facebook"
            width="z%"
          />
          <span></span>
          <span></span>
          <span></span>
          <span></span>
        </a>
      </li>
      <li class="links-list__item">
        <a href="" class="links-list__link">
          <img 
            src="@/assets/images/social/vk_icon.svg"
            alt="Vk" 
            width="100%" 
          />
          <span></span>
          <span></span>
          <span></span>
          <span></span>
        </a>
      </li>
      <li class="links-list__item">
        <a href="" class="links-list__link">
          <img
            src="@/assets/images/social/google_icon.svg"
            alt="google"
            width="100%"
          />
          <span></span>
          <span></span>
          <span></span>
          <span></span>
        </a>
      </li>
      <li class="links-list__item">
        <a href="" class="links-list__link">
          <img
            src="@/assets/images/social/twitter_icon.svg"
            alt="twitter"
            width="100%"
          />
          <span></span>
          <span></span>
          <span></span>
          <span></span>
        </a>
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.container {
  background-color: #fff;
}

.links-list {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  align-items: center;
  justify-content: center;

  &__item {
    width: 100px;
    height: 100px;
    position: relative;
    padding: 25px;
    margin: 25px;

    &:hover {
      span {
        &:nth-child(2) {
          width: 0px;
        }
        &:nth-child(3) {
          height: 100px;
        }
        &:nth-child(4) {
          width: 0px;
        }
        &:nth-child(5) {
          height: 100px;
        }
      }
    }
  }

  span {
    background-color: #000;
    position: absolute;
    transition-duration: 0.5s;

    &:nth-child(2) {
      top: 0;
      left: 0;
      width: 100px;
      height: 3px;
    }
    &:nth-child(3) {
      bottom: 0;
      right: 0;
      width: 3px;
      height: 0px;
    }
    &:nth-child(4) {
      bottom: 0;
      right: 0;
      width: 100px;
      height: 3px;
    }
    &:nth-child(5) {
      top: 0;
      left: 0;
      height: 0px;
      width: 3px;
    }
  }
}
</style>
