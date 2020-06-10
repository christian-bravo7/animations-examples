<template>
  <main class="main">
    <section class="main__body">
      <Sidebar
        v-if="isSidebarActive"
        @closeSidebar="closeSidebar"
      />
    </section>
    <section class="main__footer">
      <button @click="openSidebar">
        Change class
      </button>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator';
import Sidebar from '@/pages/vue-transitions/sidebar.vue';

@Component({
  components: {
    Sidebar
  }
})
export default class SidebarTransition extends Vue {
  isSidebarActive: boolean = false;

  openSidebar () {
    this.isSidebarActive = true
  }

  closeSidebar () {
    this.isSidebarActive = false
  }
}
</script>

<style lang="scss" scoped>
</style>
