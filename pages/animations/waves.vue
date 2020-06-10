<template>
  <main class="main">
    <section class="main__body">
      <div class="waves-container">
        <div class="waves">
          <div class="wave a" />
          <div class="wave b" />
          <div class="wave c" />
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

.main {
  overflow: hidden;
}

.waves-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 500px;
  position: relative;
  background-color: rgb(0, 119, 255);
}

.waves {
  position: absolute;
  left: -250px;
  width: 100%;
  bottom: 0;
  height: 427px;
}

.wave {
  background-image: url('~assets/waves.png');
  background-repeat: no-repeat;
  width: 150%;
  height: 100%;
  position: absolute;
  animation-name: wave;
  animation-iteration-count: infinite;
  animation-duration: 5s;
  animation-direction: alternate;
  animation-timing-function: ease-in-out;
}
.a {
  animation-delay: 0s;
  background-position: 0px -854px;
}
.b {
  animation-delay: 1s;
  background-position: 0 -427px;
}
.c {
  animation-delay: 2s;
  background-position: 0 0px;
}

@keyframes wave{
  0%{
    transform: translateX(0) translateY(0);
  }
  100%{
    transform: translateX(200px) translateY(200px);
  }
}
</style>
