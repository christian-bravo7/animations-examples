<template>
  <main class="main">
    <section class="main__body">
      <div
        class="megaman"
        :class="{ 'active': isActive }"
      />
    </section>
    <section class="main__footer">
      <button @click="toggleClass">
        Change class
      </button>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class TransitionsMySprite extends Vue {
  isActive = false;

  toggleClass () {
    this.isActive = !this.isActive
  }
}
</script>

<style lang="scss" scoped>

.megaman {
  background-image: url('~assets/megaman-sprite.png');
  width: 164px;
  height: 175px;
  transition-property: background-position-x;
  transition-duration: 1s;
  transition-timing-function: steps(4);

  &.active {
    background-position-x: 100%;
  }
}

</style>
