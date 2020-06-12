<template>
  <main class="main">
    <section class="main__body">
      <transition name="animated-box">
        <div
          v-if="isActive"
          class="box"
        />
      </transition>
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
export default class VueTransitionsConcepts extends Vue {
  isActive = false;

  toggleClass () {
    this.isActive = !this.isActive
  }
}
</script>

<style lang="scss" scoped>
.box {
  width: 200px;
  height: 200px;
  background-color: red;
}

.animated-box-enter {
  opacity: 0;
}
.animated-box-enter-active {
  transition-property: opacity;
  transition-duration: 1s;
}
.animated-box-enter-to {
  opacity: 1;
}
.animated-box-leave {
  opacity: 1;
}
.animated-box-leave-active {
  transition-property: opacity;
  transition-duration: 5s;
}
.animated-box-leave-to {
  opacity: 0;
}

</style>
