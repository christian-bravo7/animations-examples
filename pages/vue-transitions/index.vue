<template>
  <main class="main">
    <section class="main__body">
      <NuxtLink
        class="link"
        :to="{ name: 'vue-transitions-concepts' }"
      >
        Concepts
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'vue-transitions-concepts-2' }"
      >
        Concepts part II
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'vue-transitions-concepts-3' }"
      >
        Concepts part III
      </NuxtLink>
      <NuxtLink
        class="link"
        :to="{ name: 'vue-transitions-sidebar-transition' }"
      >
        Sidebar
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
