<template>
  <div>
    <h3>Componente con imagen</h3>
    <img
      :key="image"
      :src="require(`~/assets/${image}`)"
    >
    <button @click="changeImage">
      Change Image
    </button>
  </div>
</template>

<script lang="ts">

import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class ImageComponent extends Vue {

  images = [
    'minecraft-vaca.png',
    'minecraft-lobo.jpg',
    'minecraft-oveja.jpg',
    'minecraft-pig.jpg'
  ]

  randomIndex = 0

  get image () {
    const randomImage = this.images[this.randomIndex]
    return randomImage
  }

  changeImage () {
    const randomIndex = Math.floor(Math.random() * 4)
    this.randomIndex = randomIndex
  }
}

</script>

<style lang="scss" scoped>

img {
  width: 300px;
  height: auto;
  margin: 40px;
}

button {
  display: block;
}

</style>
