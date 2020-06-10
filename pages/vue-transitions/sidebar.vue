<template>
  <transition
    name="overlay"
    appear
    @after-enter="openSidebar"
  >
    <div
      class="overlay"
      @click.self="closeSidebar"
    >
      <transition
        name="sidebar"
        @after-leave="closeSidebarOverlay"
      >
        <aside
          v-if="isSidebarVisible"
          class="sidebar"
        >
          <section class="sidebar__header">
            <button
              class="sidebar__close-button"
              @click="closeSidebar"
            >
              <i class="close-button__icon">
                close
              </i>
            </button>
          </section>
          <section class="sidebar__content">
            <section class="sidebar__body">
              <p>Sidebar content</p>
            </section>
          </section>
        </aside>
      </transition>
    </div>
  </transition>
</template>

<script lang="ts">
import { Vue, Component, Emit } from 'nuxt-property-decorator';

@Component
export default class SidebarMenu extends Vue {
  isSidebarVisible: boolean = false;

  closeSidebar (): void {
    this.isSidebarVisible = false
  }

  openSidebar (): void {
    this.isSidebarVisible = true
  }

  @Emit('closeSidebar')
  closeSidebarOverlay (): void {}
}

</script>

<style lang="scss" scoped>

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 20;
  width: 100%;
  height: 100vh;
  background-color: transparent;

  &:before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    filter: opacity(0.6);
    background-color: gray;
  }
}

.sidebar {
  max-width: 320px;
  width: 100%;
  height: 100vh;
  background-color: blue;
  position: absolute;
  right: 0;
  bottom: 0;
  top: 0;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  &__header {
    padding: 16px;
    display: flex;
    justify-content: flex-end;
  }

  &__content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 16px;
    height: 100%;
  }

  &__footer {
    display: flex;
    justify-content: flex-end;
  }

  &__dark-theme {
    display: flex;
    align-items: center;
  }
}

.close-button {
  &__icon {
    font-size: 50px;
  }
}

// OVERLAY TRANSITIONS

.overlay-enter {
  opacity: 0;
}
.overlay-enter-to {
  opacity: 1;
}
.overlay-enter-active, .overlay-leave-active  {
  transition: 0.25s;
}
.overlay-leave {
  opacity: 1;
}
.overlay-leave-to {
  opacity: 0;
}

// SIDEBAR TRANSITIONS

.sidebar-enter {
  transform: translateX(100%);
  opacity: 0;
}
.sidebar-enter-to {
  transform: translateX(0);
  opacity: 1;
}
.sidebar-enter-active {
  transition: 0.25s;
}
.sidebar-leave {
  transform: translateX(0);
  opacity: 1;
}
.sidebar-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
.sidebar-leave-active {
  transition: 0.4s;
}

// .overlay-enter {
//   opacity: 0;
// }
// .overlay-enter-active {
//   transition: 1s;
// }
// .overlay-enter-to {
//   opacity: 1;
// }
// .overlay-leave {
//   opacity: 1;
// }
// .overlay-leave-active {
//   transition: 1s;
// }
// .overlay-leave-to {
//   opacity: 0;
// }

</style>
