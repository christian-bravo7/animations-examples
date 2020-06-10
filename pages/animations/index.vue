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
        Sequencial sprite moves
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'animations-loader' }"
      >
        Loader
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'animations-other-loaders' }"
      >
        Other loaders
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'animations-waves' }"
      >
        Waves
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
