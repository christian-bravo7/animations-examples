<template>
  <main class="main">
    <section class="main__body">
      <div
        class="box"
        :class="{
          'box-state-1': !isActive,
          'box-state-2': isActive,
        }"
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
export default class TransitionsBoxes extends Vue {
  isActive = false;

  toggleClass () {
    this.isActive = !this.isActive
  }
}
</script>

<style lang="scss" scoped>
.box {
  transition-property: background-color, width, height;
  transition-duration: 2s;
}

.box-state-1 {
  width: 200px;
  height: 200px;
  background-color: red;
}

.box-state-2 {
  width: 50px;
  height: 50px;
  background-color: blue;
}
</style>
