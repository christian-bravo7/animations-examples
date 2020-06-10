<template>
  <main class="main">
    <section class="main__body">
      <div>Your sprite here</div>
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

</style>
