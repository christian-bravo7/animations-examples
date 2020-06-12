<template>
  <main class="main">
    <section class="main__body">
      <transition name="scaleOut" mode="out-in">
        <div
          v-if="isActive"
          key="box"
          class="box"
        />
        <div
          v-if="!isActive"
          key="circle"
          class="circle"
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

@Component({
  transition: 'scaleOut'
})
export default class VueTransitionsConcepts2 extends Vue {
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

.circle {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background-color: blueviolet;
}

.scaleOut-enter {
  transform: scale(0);
}
.scaleOut-enter-active {
  transition-property: transform;
  transition-duration: 2s;
}
.scaleOut-enter-to {
  transform: scale(1);
}
.scaleOut-leave {
  transform: scale(1);
}
.scaleOut-leave-active {
  transition-property: transform;
  transition-duration: 2s
}
.scaleOut-leave-to {
  transform: scale(0);
}

.xxxxxxx-enter-active {}
.xxxxxxx-leave-active {}

</style>
