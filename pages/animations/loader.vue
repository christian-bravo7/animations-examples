<template>
  <main class="main">
    <section class="main__body">
      <div class="loader-container">
        <div class="loader" />
      </div>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class AnimationsLoader extends Vue {}
</script>

<style lang="scss" scoped>

.loader-container {
  display: flex;
  justify-content: center;
}

.loader {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border: 3px solid rgba(cornflowerblue, 0.4);
  border-left-color: cornflowerblue;

  animation-name: spinner;
  animation-duration: 1s;
  animation-iteration-count: infinite;
}

@keyframes spinner {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

</style>
