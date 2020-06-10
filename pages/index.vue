<template>
  <main class="main">
    <section class="main__body">
      <NuxtLink
        class="link"
        :to="{ name: 'transitions' }"
      >
        Transitions
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'animations' }"
      >
        Animations
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'vuetransitions' }"
      >
        Vue transitions
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
export default class IndexPage extends Vue {}
</script>
