<template>
  <div>
    <div class="card">
      <img :src="`http://image.tmdb.org/t/p/w342/${singleFilm.backdrop_path}`" alt="">
      <p>Titolo: {{singleFilm.title}}</p>
      <p>Titolo originale: {{singleFilm.original_title}}</p>
      <p>Lingua: {{singleFilm.original_language}}</p>
      <p>Voto: {{singleFilm.vote_average}}</p>
      
    </div>
  </div>
</template>

<script>
  export default {
    name: 'CardFilm',
    props: {
      singleFilm: Object,
    }
  }
</script>

<style lang="scss" scoped>
  .card{
    width: calc(100%);
  }
</style>