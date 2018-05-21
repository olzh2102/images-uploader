<template>
  <div class="image-container">
    <img v-for="(image, index) in allImages" :key="index" :src="image.link" />
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'ImageList',
  computed: mapGetters(['allImages']),
  methods: mapActions(['fetchImages']),
  created() {
    this.fetchImages()
  },
}
</script>

<style scoped>
.image-container {
  column-count: 2;
  column-gap: 0;
}

img {
  max-width: 100%;
  padding: 5px;
}
</style>
