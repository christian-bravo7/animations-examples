<template>
  <main class="main">
    <section class="main__body">
      <NuxtLink
        class="link"
        :to="{ name: 'animations-concepts' }"
      >
        Conceptos
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'animations-sprites-moves' }"
      >
        Complex sprite moves
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'animations-my-sprite' }"
      >
        My Sprite
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'animations-other-examples' }"
      >
        Other examples
      </NuxtLink>
    </section>
    <section class="main__footer">
      <h1>Hello world!</h1>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class TransitionsIndexPage extends Vue {}
</script>
