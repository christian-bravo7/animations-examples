<template>
  <main class="main">
    <section class="main__body">
      <section>
        <h2>Transiciones</h2>
        <div class="pelota" />
      </section>
      <section>
        <h2>Transiciones en multiples elementos</h2>
        <div class="canasta">
          <div class="pelota-pequena pelota_a">
            Hola
          </div>
          <div class="pelota-pequena pelota_b">
            Mundo
          </div>
        </div>
      </section>
      <section>
        <h2>Transformaciones</h2>
        <div class="canasta_3">
          <div class="pelota-pequena pelota_a_3">
            Hola
          </div>
          <div class="pelota-pequena pelota_b_3">
            Mundo
          </div>
        </div>
      </section>
      <section>
        <h2>Transformaciones: Rotate</h2>
        <div class="container container_1">
          <div class="cuadrado cuadradoX">
            Rotacion en X
          </div>
          <div class="cuadrado cuadradoY">
            Rotacion en Y
          </div>
          <div class="cuadrado cuadradoZ">
            Rotacion en Z
          </div>
          <div class="cuadrado cuadrado3D">
            Rotacion 3D
          </div>
        </div>
      </section>
      <section>
        <h2>Transformaciones: Translate</h2>
        <div class="container container_2">
          <div class="cuadrado cuadrado_2">
            Hola Mundo
          </div>
        </div>
      </section>
      <section>
        <h2>Transformaciones: Scale</h2>
        <div class="container container_3">
          <div class="cuadrado cuadrado_3">
            Hola Mundo
          </div>
        </div>
      </section>
      <section>
        <h2>Transformaciones: Skew</h2>
        <div class="container container_4">
          <div class="cuadrado cuadrado_4">
            Hola Mundo
          </div>
        </div>
      </section>
      <section>
        <h2>Punto de transformacion</h2>
        <div class="container container_5">
          <div class="cuadrado cuadrado--a">
            Hola Mundo
          </div>
          <div class="cuadrado cuadrado--b">
            Hola Mundo
          </div>
          <div class="cuadrado cuadrado--c">
            Hola Mundo
          </div>
        </div>
      </section>
    </section>
  </main>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class TransitionsTransformations extends Vue {}
</script>

<style lang="scss" scoped>

h2 {
  margin: 20px 0;
}

.cuadrado {
  width: 200px;
  height: 200px;
  margin: 20px;
  padding: 20px;
  text-align: center;
  background-color: #7dc900;
  color: white;
  box-sizing: border-box;
  transition: 1s;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid red;
  padding: 30px;
}

/*Transiciones */

.pelota {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-color: red;
  transition-property: width, height;
  transition-duration: 1s;
  transition-delay: 0s;
  transition-timing-function: ease;
}

.pelota:hover {
  width: 200px;
  height: 200px;
}

/*Transiciones a varios elementos*/

.pelota-pequena {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  transition: 2s;
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}

.canasta {
  border: 1px solid red;
  position: relative;
  height: 100px;
}

.canasta:hover .pelota_a {
  left: calc(50% - 100px);
  background-color: red;
}

.canasta:hover .pelota_b {
  right: calc(50% - 100px);
  background-color: blue;
}

.pelota_a {
  background-color: blue;
  left: 0;
}
.pelota_b {
  background-color: red;
  right: 0;
}

/*Clase 3 - Transformaciones*/

.canasta_3 {
  border: 1px solid red;
  position: relative;
  height: 100px;
  transform: rotate(5deg) skew(40deg) translate(200px) scale(0.75);
}
.canasta_3:hover .pelota_a_3 {
  left: calc(50% - 100px);
  background-color: red;
}
.canasta_3:hover .pelota_b_3 {
  right: calc(50% - 100px);
  background-color: blue;
}
.pelota_a_3 {
  background-color: blue;
  left: 0;
}
.pelota_b_3 {
  background-color: red;
  right: 0;
}

/*Transformaciones: Rotate*/
.container_1:hover .cuadradoX {
  transform: rotateX(45deg)
}
.container_1:hover .cuadradoY {
  transform: rotateY(45deg)
}
.container_1:hover .cuadradoZ {
  transform: rotateZ(45deg)
}
.container_1:hover .cuadrado3D {
  transform: rotate3d(1,1,1, 45deg)
}

/*Transformaciones: Translate*/

.container_2 {
  perspective: 20px;
  perspective-origin: center;
}

.container_2:hover .cuadrado_2 {
  // transform: translate(100px, 50px);
  transform: translateZ(10px);
}

/*Transformaciones: Scale*/

.container_3:hover .cuadrado_3{
  transform: scale(0.5, 1.4);
  // transform: scaleX(0.5);
  // transform: scaleY(0.5);
}

/*Transformaciones: Skew*/

.container_4:hover .cuadrado_4 {
  transform: skewY(30deg);
  // transform: skew(30deg, 15deg);
}

/*Transformaciones: Punto de transformacion*/

.container_5 {

  &:hover .cuadrado{
    &--a {
      transform-origin: 100%;
      transform: rotateY(45deg);
    }

    &--b {
      transform-origin: top;
      transform: rotateX(45deg);
    }

    &--c {
      transform-origin: right top;
      transform: rotate(-45deg);
    }
  }
}

</style>
