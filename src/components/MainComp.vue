<template>
  <div>
    <FilmsList />
    <SeriesList />
  </div>
</template>

<script>
import FilmsList from './FilmsList.vue'
import SeriesList from './SeriesList.vue'

export default {
    name: 'MainComp',
    components: {
      FilmsList,
      SeriesList,
  }
}
</script>

<style lang="scss" scoped>

</style>