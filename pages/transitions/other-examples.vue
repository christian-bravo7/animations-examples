<template>
  <main class="main">
    <section class="main__body">
      <div class="buttons-container">
        <button class="button button__1">Hover me!</button>
        <button class="button button__2">Hover me!</button>
        <button class="button button__3">Hover me!</button>
        <button class="button button__4">Hover me!</button>
        <button class="button button__5">Hover me!</button>
        <button class="button button__6">Hover me!</button>
      </div>
      <div class="buttons-container">
        <button class="button-clicked button-clicked--press" @click="toggleActiveClass">Press me!</button>
        <button class="button-clicked button-clicked--switch" @click="toggleActiveClass" />
        <button class="button-clicked button-clicked--switch active" @click="toggleActiveClass" />
        <button class="button-clicked button-clicked--twitter" @click="toggleActiveClass" />
      </div>
      <div>
        <div class="items-container">
          <div class="item">Item</div>
          <div class="item">Item</div>
          <div class="item">Item</div>
          <div class="item">Item</div>
          <div class="item">Item</div>
          <div class="item">Item</div>
          <div class="item">Item</div>
          <div class="item">Item</div>
        </div>
        <div class="items-container items-container-2">
          <div class="item item-2">Item</div>
          <div class="item item-2">Item</div>
          <div class="item item-2">Item</div>
          <div class="item item-2">Item</div>
          <div class="item item-2">Item</div>
          <div class="item item-2">Item</div>
          <div class="item item-2">Item</div>
          <div class="item item-2">Item</div>
        </div>
      </div>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class OtherExamples extends Vue {
  isActive = false;

  toggleClass () {
    this.isActive = !this.isActive
  }

  toggleActiveClass (event) {
    event.target.classList.toggle('active')
  }
}
</script>

<style lang="scss" scoped>
.main__body {
  flex-direction: row;
}
.buttons-container {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 200px;
}

.button {
  background-color: cornflowerblue;
  box-shadow: none;
  transition: 0.4s;
  margin-bottom: 10px;
  border-radius: 0;

  &__1 {
    &:hover {
      background-color: white;
      border: 1px solid cornflowerblue;
      color: cornflowerblue;
    }
  }

  &__2 {
    display: flex;
    justify-content: center;
    position: relative;
    background-color: white;
    color: cornflowerblue;
    letter-spacing: 0;

    &:hover {
      letter-spacing: 5px;
    }

    &:after {
      content: '';
      background-color: cornflowerblue;
      position: absolute;
      bottom: 0%;
      transition-property: width;
      transition-duration: 0.4s;
      height: 2px;
      width: 0%;
    }

    &:hover:after {
      width: 70%;
    }
  }

  &__3 {
    border: 1px solid transparent;
    outline-width: 1px;
    outline-color: cornflowerblue;
    outline-style: solid;
    outline-offset: 0px;
    text-shadow: none;
    background-color: white;
    color: cornflowerblue;
    outline-offset: 0px;

    &:hover {
      border-color: cornflowerblue;
      outline-color: transparent;
      outline-offset: 25px;
    }
  }

  &__4 {
    border: 1px solid cornflowerblue;
    background-color: transparent;
    color: cornflowerblue;
    position: relative;

    &:hover {
      color: white;
    }

    &:after {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 0px;
      height: 100%;
      background-color: cornflowerblue;
      transition: 0.4s;
      z-index: -1;
    }

    &:hover:after {
      width: 100%;
    }
  }

  &__5 {
    border: 1px solid cornflowerblue;
    background-color: transparent;
    color: cornflowerblue;
    position: relative;

    &:hover {
      color: white;
    }

    &:after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      width: 0px;
      height: 100%;
      background-color: cornflowerblue;
      transition: 0.4s;
      z-index: -1;
    }

    &:hover:after {
      width: 100%;
    }
  }

  &__6 {
    border: 1px solid cornflowerblue;
    background-color: transparent;
    color: cornflowerblue;

    &:hover {
      transform: scale(1.1);
    }
  }
}

.button-clicked {
  margin-bottom: 20px;

  &--press {
    background-color: #ffaa42;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    margin-bottom: 20px;
    transition: 0.5s;
    outline: none;
    box-shadow: 0px 0px 24px 1px #633600;

    &.active {
      background-color: darkorange;
      box-shadow: 0px 0px 10px 1px #633600;
      transform: scale(0.9);
    }
  }

  &--switch {
    width: 80px;
    height: 30px;
    border-radius: 20px;
    position: relative;
    outline: none;
    background-color: #979797;
    box-shadow: none;
    display: flex;
    align-items: center;

    &:before {
      content: '';
      position: absolute;
      left: 2px;
      height: 28px;
      width: 28px;
      background-color: white;
      border-radius: 50%;
      transition: 0.4s;
    }

    &.active {
      background-color: #4e88f5;
      box-shadow: 0px 0px 5px 0px #2256b8;

      &:before {
        left: calc(100% - 28px);
      }
    }
  }

  &--twitter{
    width: 100px;
    height: 100px;
    background-image: url("~assets/twitter-corazon.png");
    background-repeat: no-repeat;
    transition: 1s;
    transition-timing-function: steps(28);
    background-position: 0 0;
    background-color: transparent;
    box-shadow: none;

    &.active {
      background-position: -2800px 0;
    }
  }
}

.items-container {
  width: 500px;
  height: 250px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  gap: 10px;
  grid-auto-rows: auto;
  margin-bottom: 50px;
}

.item {
  padding: 20px;
  cursor: default;
  background-color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 20px;
  box-shadow: 0px 0px 8px -4px black;
  transition: 0.5s;

  &:hover {
    transform: scale(1.2);
  }
}

.items-container-2 {
  &:hover .item-2 {
    opacity: 0.3;
  }
  &:hover .item-2:hover {
    opacity: 1;
    transform: scale(1.1);
  }
}

.item-2 {
  background-color: #4e88f5;
}


</style>
