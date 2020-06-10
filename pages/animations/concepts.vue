<template>
  <main class="main">
    <section class="main__body">
      <div class="box-container">
        <div
          class="box"
          :class="{ 'animated-box': isActive }"
        />
      </div>
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
export default class AnimationsConcepts extends Vue {
  isActive = false;

  toggleClass () {
    this.isActive = !this.isActive
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
}

</style>
