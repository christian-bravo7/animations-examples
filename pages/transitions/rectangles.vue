<template>
  <main class="main">
    <section class="main__body">
      <div
        class="rectangle rectangle--is-bezier rectangle-ease"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        ease
      </div>
      <div
        class="rectangle rectangle--is-bezier rectangle-ease-in"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        ease-in
      </div>
      <div
        class="rectangle rectangle--is-bezier rectangle-ease-in-out"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        ease-in-out
      </div>
      <div
        class="rectangle rectangle--is-bezier rectangle-linear"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        linear
      </div>
      <div
        class="rectangle rectangle-step-start"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        step-start
      </div>
      <div
        class="rectangle rectangle-step-end"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        step-end
      </div>
      <div
        class="rectangle rectangle-step-5"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        steps(5)
      </div>
      <div
        class="rectangle rectangle-step-10"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        steps(10)
      </div>
      <div
        class="rectangle rectangle-step-jump-end"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        Jump end
      </div>
      <div
        class="rectangle rectangle-step-jump-start"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        Jump start
      </div>
      <div
        class="rectangle rectangle-step-jump-both"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        Jump both
      </div>
      <div
        class="rectangle rectangle-step-jump-none"
        :class="{'rectangle--is-shrink': stateChanged }"
      >
        Jump none
      </div>
    </section>
    <section class="main__footer">
      <button @click="changeState">
        Change elements states
      </button>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class TransitionsCircles extends Vue {
  stateChanged = false;

  changeState () {
    this.stateChanged = !this.stateChanged
  }
}
</script>

<style lang="scss" scoped>

.rectangle {
  display: flex;
  align-items: center;
  padding: 5px;
  margin-bottom: 2px;
  width: 200px;
  height: 50px;
  background-color: crimson;
  color: white;

  transition: width 2s;

  &:hover, &--is-shrink {
    width: 50px;
  }

  &--is-bezier {
    background-color: chocolate;
  }

  &-ease {
    transition-timing-function: ease;
  }
  &-ease-in {
    transition-timing-function: ease-in;
  }
  &-ease-out {
    transition-timing-function: ease-out;
  }
  &-ease-in-out {
    transition-timing-function: ease-in-out;
  }
  &-linear {
    transition-timing-function: linear;
  }
  &-step-start {
    transition-timing-function: step-start;
  }
  &-step-end {
    transition-timing-function: step-end;
  }
  &-step-5 {
    transition-timing-function: steps(5);
  }
  &-step-10 {
    transition-timing-function: steps(10);
  }
  &-step-jump-start {
    transition-timing-function: steps(3, jump-start);
  }
  &-step-jump-end {
    transition-timing-function: steps(3, jump-end);
  }
  &-step-jump-both {
    transition-timing-function: steps(3, jump-both);
  }
  &-step-jump-none {
    transition-timing-function: steps(4, jump-none);
  }

}

</style>
