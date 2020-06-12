<template>
  <main class="main">
    <section class="main__body">
      <transition name="scaleOut">
        <component :is="myComponent" />
      </transition>
    </section>
    <section class="main__footer">
      <button @click="toggleComponent">
        Change class
      </button>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

import TextComponent from '@/pages/vue-transitions/TextComponent.vue';
import ImageComponent from '@/pages/vue-transitions/ImageComponent.vue';

@Component({
  components: {
    TextComponent,
    ImageComponent
  }
})
export default class VueTransitionsConcepts3 extends Vue {
  isText = true;

  get myComponent () {
    return this.isText ? 'TextComponent' : 'ImageComponent'
  }

  toggleComponent () {
    this.isText = !this.isText
  }
}
</script>

<style lang="scss" scoped>
.box {
  width: 200px;
  height: 200px;
  background-color: red;
}

.scaleOut-enter {
  transform: scale(0);
}
.scaleOut-enter-active {
  transition-property: transform;
  transition-duration: 2s;
}
.scaleOut-enter-to {
  transform: scale(1);
}
.scaleOut-leave {
  transform: scale(1);
}
.scaleOut-leave-active {
  transition-property: transform;
  transition-duration: 2s
}
.scaleOut-leave-to {
  transform: scale(0);
}

// .xxxxxxx-enter {}
// .xxxxxxx-enter-active {}
// .xxxxxxx-enter-to {}
// .xxxxxxx-leave {}
// .xxxxxxx-leave-active {}
// .xxxxxxx-leave-to {}

</style>
