<template>
  <div>
    <div class="card">
      <img :src="`http://image.tmdb.org/t/p/w342/${singleSerie.backdrop_path}`" alt="">
      <p>Titolo: {{singleSerie.original_name}}</p>
      <p>Titolo originale: {{singleSerie.original_title}}</p>
      <p>Lingua: {{singleSerie.original_language}}</p>
      <p>Voto: {{singleSerie.vote_average}}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'CardSerie',
    props: {
      singleSerie: Object,
    }
  }
</script>

<style lang="scss" scoped>
  .card{
    width: calc(100%);
  }
</style>