<template>
  <div class="container">
    <ul class="list">
      <li class="list__item">
        <label class="list-label">
          List item 1
          <input type="checkbox" class="list-label__input">
          <span class="list-label__check"></span>
        </label>
      </li>
      <li class="list__item">
        <label class="list-label">
          List item 2
          <input type="checkbox" class="list-label__input">
          <span class="list-label__check"></span>
        </label>
      </li>
      <li class="list__item">
        <label class="list-label">
          List item 3
          <input type="checkbox" class="list-label__input">
          <span class="list-label__check"></span>
        </label>
      </li>
      <li class="list__item">
        <label class="list-label">
          List item 4
          <input type="checkbox" class="list-label__input">
          <span class="list-label__check"></span>
        </label>
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
  .container {
    background-color: #00080c;
  }

  .list {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background: #00151f;
    padding: 10px 20px;
    width: 200px;
    border: 1px solid rgba(0, 0, 0, .5);

    &__item {
      position: relative;
      padding: 15px 0;
      border-bottom: 1px solid rgba(0, 0, 0, 0.2);
      &:last-child {
        border-bottom: none;
      }
    }
  }

  .list-label {
    font-size: 18px;
    color: #fff;
    padding-left: 30px;
    cursor: pointer;

    &__input {
      opacity: 0;
      cursor: pointer;
    }

    &__check {
      position: absolute;
      top: 12px;
      left: 0;
      width: 20px;
      height: 20px;
      background: #000;
      display: block;
      border: 2px solid #000;
      border-radius: 4px;
      &:before {
        content: '';
        position: absolute;
        top: 3px;
        left: 3px;
        right: 3px;
        bottom: 3px;
        background: #000b10;
        border-radius: 2px;
        transition: .5s;
        transform: translateX(150px);
      }
    }
  }

  .list-label__input:checked ~ .list-label__check:before {
    background: #adff00;
    box-shadow: 0 0 15px #adff00;
    transform: translateX(0);
  }
</style>
