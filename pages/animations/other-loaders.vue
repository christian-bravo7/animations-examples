<template>
  <main class="main">
    <section class="main__body">
      <div class="loaders">
        <div class="loader-container">
          <div class="loader circle" />
          <h5>Circle</h5>
        </div>
        <div class="loader-container">
          <div class="loader multiple-circles" />
          <h5>Multiple Circles</h5>
        </div>
        <div class="loader-container">
          <div class="loader internal-circle" />
          <h5>internal circle</h5>
        </div>
        <div class="loader-container">
          <div class="loader circle-slices" />
          <h5>Slices</h5>
        </div>
        <div class="loader-container">
          <div class="loader bars" />
          <h5>Bars</h5>
        </div>
        <div class="loader-container">
          <div class="loader pulse-effect" />
          <h5>Pulse effect</h5>
        </div>
        <div class="loader-container">
          <div class="loader external-circle" />
          <h5>external circle</h5>
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

.loaders {
  display: grid;
  grid-template-columns: repeat(5, 200px);
  grid-auto-rows: 200px;
}

.loader-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.loader {
  width: 32px;
  height: 32px;
  margin: 20px auto;
}

/* Spinner Circle Rotation */

.circle {
  border: 4px rgba(cornflowerblue, 0.25) solid;
  border-top-color: cornflowerblue;
  border-radius: 50%;
  animation: circle-rotation .6s infinite linear;
}

@keyframes circle-rotation {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

/* Multiple circles */

.multiple-circles, .multiple-circles:before, .multiple-circles:after {
  border-radius: 50%;
  background-color: cornflowerblue;
  width: 15px;
  height: 15px;
  display: inline-block;
}

.multiple-circles {
  position: relative;
  background-color: rgba(cornflowerblue, 1);
  opacity: 1;
  animation: circles-fade 1s infinite linear;
}

.multiple-circles:before, .multiple-circles:after {
  content: '';
  position: relative;
  opacity: 0.25;
}

.multiple-circles:before {
  left: 30px;
  top: 0px;
  animation: right-circle-fade 1s infinite linear;
}

.multiple-circles:after {
  left: -30px;
  top: -23px;
  animation: left-circle-fade 1s infinite linear;
}

@keyframes circles-fade {
  0% { opacity: 1; }
  33% {  opacity: 0.25; }
  66% { opacity: 0.25; }
  100% {  opacity: 1; }
}

@keyframes right-circle-fade {
  0% { opacity: 0.25; }
  33% { opacity: 1; }
  66% { opacity: 0.25; }
}

@keyframes left-circle-fade {
  33% { opacity: 0.25; }
  66% { opacity: 1; }
  100% { opacity: 0.25; }
}

/* Spinner internal-circle */

.internal-circle {
  background-color: cornflowerblue;
  border-radius: 50%;
  position: relative;
  animation: internal-circle-rotation .6s infinite linear;
}

.internal-circle:after {
  content: '';
  border-radius: 50%;
  position: absolute;
  display: block;
  width: 10px;
  height: 10px;
  left: 5px;
  top: 5px;
  background-color: lighten(cornflowerblue,100%);
}

@keyframes internal-circle-rotation {
  from { transform: rotate(0deg); }
  to { transform: rotate(359deg); }
}

/* Spinner Slices */

.circle-slices {
  border-radius: 50%;
  border-top: 16px rgba(cornflowerblue,0.75) solid;
  border-left: 16px rgba(cornflowerblue,0.25) solid;
  border-bottom: 16px rgba(cornflowerblue,0.25) solid;
  border-right: 16px rgba(cornflowerblue,0.25) solid;
  animation: circle-slice-effect 1s infinite linear;
}

@keyframes circle-slice-effect {
  0% {
  border-top-color: rgba(cornflowerblue,0.75);
  border-right-color: rgba(cornflowerblue,0.25);
  border-bottom-color: rgba(cornflowerblue,0.25);
  border-left-color: rgba(cornflowerblue,0.25);
  }
  25% {
  border-top-color: rgba(cornflowerblue,0.25);
  border-right-color: rgba(cornflowerblue,0.75);
  border-bottom-color: rgba(cornflowerblue,0.25);
  border-left-color: rgba(cornflowerblue,0.25);
  }
  50% {
  border-top-color: rgba(cornflowerblue,0.25);
  border-right-color: rgba(cornflowerblue,0.25);
  border-bottom-color: rgba(cornflowerblue,0.75);
  border-left-color: rgba(cornflowerblue,0.25);
  }
  75% {
  border-top-color: rgba(cornflowerblue,0.25);
  border-right-color: rgba(cornflowerblue,0.25);
  border-bottom-color: rgba(cornflowerblue,0.25);
  border-left-color: rgba(cornflowerblue,0.75);
  }
  100% {
  border-top-color: rgba(cornflowerblue,0.75);
  border-right-color: rgba(cornflowerblue,0.25);
  border-bottom-color: rgba(cornflowerblue,0.25);
  border-left-color: rgba(cornflowerblue,0.25);
  }
}

/* Spinner Bars */

.bars {
  position: relative;
  width: 10px;
  border: 1px cornflowerblue solid;
  background-color: rgba(cornflowerblue,0.25);
  animation: bars-effect 1s infinite linear;
}

.bars:after, .bars:before {
  content:'';
  position: absolute;
  width: inherit;
  height: inherit;
  border: inherit;
  background-color: inherit;
  top: -1px;
}

.bars:before {
  left: -20px;
  animation: left-bar-effect 1s infinite linear;
}

.bars:after {
  right: -20px;
  animation: right-bar-effect 1s infinite linear;
}

@keyframes left-bar-effect {
  0% {
  transform: scale(1,1);
  }
  25% {
  transform: scale(1,1.25);
  }
  50% {
  transform: scale(1,0.75);
  }
  75% {
  transform: scale(1,1);
  }
  100% {
  transform: scale(1,1);
  }
}
@keyframes bars-effect {
  0% {
  transform: scale(1,1);
  }
  25% {
  transform: scale(1,1);
  }
  50% {
  transform: scale(1,1.25);
  }
  75% {
  transform: scale(1,1);
  }
  100% {
  transform: scale(1,1);
  }
}
@keyframes right-bar-effect {
  0% {
  transform: scale(1,1);
  }
  25% {
  transform: scale(1,1);
  }
  50% {
  transform: scale(1,0.75);
  }
  75% {
  transform: scale(1,1.25);
  }
  100% {
  transform: scale(1,1);
  }
}

/* Spinner pulse effect */

.pulse-effect {
  border-radius: 50%;
  position: relative;
  opacity: 1;
}

.pulse-effect:before, .pulse-effect:after  {
  content:'';
  border: 1px cornflowerblue solid;
  border-radius: 50%;
  width: 100%;
  height: 100%;
  position: absolute;
  left:0px;
}

.pulse-effect:before {
  transform: scale(1,1);
  opacity: 1;
  animation: externalRing 0.6s infinite linear;
}

.pulse-effect:after {
  transform: scale(0,0);
  opacity: 0;
  animation: internalRing 0.6s infinite linear;
}

@keyframes internalRing {
  from { transform: scale(0.5,0.5); opacity: 0; }
  to { transform: scale(1,1); opacity: 1; }
}

@keyframes externalRing {
  from { transform: scale(1,1); opacity: 1; }
  to { transform: scale(1.5,1.5); opacity: 0; }
}

/* Spinner external cricle */

.external-circle {
  position: relative;
  border: 1px cornflowerblue solid;
  border-radius: 50%;
  animation: external-circle-effect 0.6s infinite linear;
}

.external-circle:before, .external-circle:after {
  content: '';
  position: absolute;
  width: 10px;
  height: 10px;
  background-color: cornflowerblue;
  border-radius: 50%;
}

.external-circle:before {
  top: calc( 50% - 5px );
  left: calc( 50% - 5px );
}

.external-circle:after {
  top: -1px;
  left: -1px;
}

@keyframes external-circle-effect {
  from { transform: rotate(0deg); }
  to { transform: rotate(359deg); }
}

</style>
