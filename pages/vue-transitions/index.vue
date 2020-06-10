<template>
  <main class="main">
    <section class="main__body">
      <NuxtLink
        class="link"
        :to="{ name: 'vue-transitions-sidebar-transition' }"
      >
        Sidebar
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'vue-transitions-rectangles' }"
      >
        Rectangles
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'vue-transitions-transformations' }"
      >
        Transitions + transformations
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
export default class VueTransitionsIndexPage extends Vue {}
</script>
