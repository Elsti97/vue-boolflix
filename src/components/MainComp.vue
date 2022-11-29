<template>
  <main>
    <FilmsList :arrayFilm2="arrayFilm" />
    <SeriesList />
  </main>
</template>

<script>
import FilmsList from './FilmsList.vue'
import SeriesList from './SeriesList.vue'

export default {
  name: 'MainComp',
  components: {
      FilmsList,
      SeriesList,
  },
  props: {
    arrayFilm: Array,
  }
}
</script>

<style lang="scss" scoped>

</style>