<template>
  <main class="main">
    <section class="main__body">
      <div class="player-container">
        <div class="player moving" />
      </div>
    </section>
    <section class="main__footer">
      <button @click="doAnimation('punch')">
        Punch
      </button>
      <button @click="doAnimation('kick')">
        Kick
      </button>
      <button @click="doAnimation('reverse-kick')">
        Reverse kick
      </button>
      <button @click="doAnimation('player-down')">
        Down
      </button>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class TransitionsMySprite extends Vue {
  isActive = false;

  doAnimation (animationName: string) {
    const player = document.querySelector('.player') as HTMLElement
    player!.classList.remove('moving')
    player!.classList.add(animationName)

    window.setTimeout(() => {
      player!.classList.remove(animationName)
      player!.classList.add('moving')
    }, 500)
  }
}
</script>

<style lang="scss" scoped>

button {
  margin: 0 10px;
}

.player-container {
  display: flex;
  justify-content: center;
}

.player {
  position: absolute;
  bottom: 112px;
  width: 70px;
  height: 80px;
  background-image: url('~assets/street-fighter-player.png');

  &.punch {
    animation-name: punch;
    animation-duration: 0.15s;
    animation-timing-function: steps(3);
  }
  &.kick {
    animation-name: kick;
    animation-duration: 0.5s;
    animation-timing-function: steps(5);
  }
  &.reverse-kick {
    animation-name: reverse-kick;
    animation-duration: 0.5s;
    animation-timing-function: steps(5);
  }
  &.player-down {
    animation-name: player-down;
    animation-duration: 0.5s;
    animation-timing-function: steps(1);
    animation-iteration-count: infinite;
  }
  &.moving {
    animation-name: moving;
    animation-duration: 0.5s;
    animation-timing-function: steps(4);
    animation-iteration-count: infinite;
  }
}

@keyframes player-down {
  from {
    background-position: 0px -720px;
  }
  to {
    background-position: -70px -720px;
  }
}

@keyframes reverse-kick {
  from {
    background-position: 0px -560px;
  }
  to {
    background-position: -350px -560px;
  }
}

@keyframes moving {
  from {
    background-position: 0px -80px;
  }
  to {
    background-position: -280px -80px;
  }
}

@keyframes kick {
  from {
    background-position: 0px -480px;
  }
  to {
    background-position: -350px -480px;
  }
}

@keyframes punch {
  from {
    background-position: 0px -160px;
  }
  to {
    background-position: -210px -160px;
  }
}

</style>
