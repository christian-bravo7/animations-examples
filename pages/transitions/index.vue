<template>
  <main class="main">
    <section class="main__body">
      <NuxtLink
        class="link"
        :to="{ name: 'transitions-boxes' }"
      >
        Boxes
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'transitions-rectangles' }"
      >
        Rectangles
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'transitions-birds' }"
      >
        Birds
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'transitions-my-sprite' }"
      >
        My Sprite
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'transitions-other-examples' }"
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
