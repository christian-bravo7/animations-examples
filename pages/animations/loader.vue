<template>
  <main class="main">
    <section class="main__body">
      <div class="loader-container">
        <div>
          loaders?
        </div>
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

</style>
