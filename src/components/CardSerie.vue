<template>
  <div>
    <div class="card">
      <img :src="`http://image.tmdb.org/t/p/w342/${singleSerie.poster_path}`" alt="">
      <div class="titles">
        <p>Titolo: {{singleSerie.name}}</p>
        <p>Titolo originale: {{singleSerie.original_name}}</p>
        <p>Lingua: {{singleSerie.original_language}}</p>
        <p>Voto: {{singleSerie.vote_average}}</p>
      </div>

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
  position: relative;
}
.titles{
  display: none;
  h4{
    display: inline;
  }
}
.card:hover .titles{
  padding: 2rem 1rem 0;
  width: 100%;
  height: 100%;
  background-color: black;
  color: white;
  opacity: 0.9;
  position: absolute;
  display: inline;
  overflow: auto;
}
</style>