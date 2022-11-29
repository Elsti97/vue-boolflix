<template>
  <div class="d-flex flex-wrap">
    <CardFilm v-for="(elem, index) in arrayFilm2" :key="index" :singleFilm="elem" class="d-flex flex-wrap" />
</div>
</template>

<script>
import CardFilm from './CardFilm.vue'

export default {
    name: 'FilmsList',
    components: {
      CardFilm,
  },
  props: {
    arrayFilm2: Array,
  }
}
</script>

<style lang="scss" scoped>

</style>