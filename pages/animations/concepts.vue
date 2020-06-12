<template>
  <main class="main">
    <section class="main__body">
      <div class="box-container">
        <div
          class="box"
          :class="{ 'animated-box': isActive, 'paused': isPaused }"
        />
      </div>
    </section>
    <section class="main__footer">
      <button @click="toggleClass">
        Change class
      </button>
      <button @click="pauseAnimation">
        Pause animation
      </button>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class AnimationsConcepts extends Vue {
  isActive = false;
  isPaused = false;

  toggleClass () {
    this.isActive = !this.isActive
  }

  pauseAnimation () {
    this.isPaused = !this.isPaused
  }
}
</script>

<style lang="scss" scoped>

.box-container {
  position: relative;
  border: 1px solid black;
  height: 200px;
}

.box {
  width: 200px;
  height: 100%;
  background-color: red;
  position: absolute;
  left: 0;

  &.animated-box {
    animation-name: move;
    animation-duration: 1s;
    animation-fill-mode: both;
    animation-direction: alternate-reverse;
    animation-iteration-count: infinite;
  }

  &.paused {
    animation-play-state: paused;
  }
}

@keyframes move {

  from {
    left: 0;
  }

  to {
    left: calc(100% - 200px);
  }

}

</style>
