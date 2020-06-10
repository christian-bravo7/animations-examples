<template>
  <main class="main">
    <section class="main__body">
      <div class="birds-container">
        <div
          class="bird-sprite"
          :class="{ 'bird-sprite-transitioned': isActive }"
        />
        <div
          class="bird-sprite-2"
          :class="{ 'bird-sprite-2-transitioned': isActive }"
        />
      </div>
    </section>
    <section class="main__footer">
      <button @click="toggleClass">
        Change state
      </button>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class TransitionsBirds extends Vue {
  isActive = false;

  toggleClass () {
    this.isActive = !this.isActive
  }
}
</script>

<style lang="scss" scoped>
.birds-container {
  display: flex;
  justify-content: center;
}

.bird-sprite {
  display: inline-block;
  width: 409px;
  height: 550px;
  background-image: url('~assets/bird-sprite.jpg');
  background-repeat: no-repeat;
  background-position: 0% 0%;
  transition: background-position 0.5s steps(4);
}

.bird-sprite-transitioned {
  background-position: 98% 0%;
}

.bird-sprite-2 {
  display: inline-block;
  width: 409px;
  height: 550px;
  background-image: url('~assets/bird-sprite.jpg');
  background-repeat: no-repeat;
  background-position: 0% 42%;
  transition: background-position 0.5s steps(4);
}

.bird-sprite-2-transitioned {
  background-position: 98% 42%;
}

</style>
