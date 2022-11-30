<template>
  <div>
    <div class="card">
      <img :src="`http://image.tmdb.org/t/p/w342/${singleSerie.poster_path}`" alt="">
      <div class="titles">
        <p>Titolo: {{singleSerie.name}}</p>
        <p>Titolo Originale: {{singleSerie.original_name}}</p>
        <img v-if="flags.includes(singleSerie.original_language)" :src="require(`../assets/${singleSerie.original_language}.svg`)" class="flag">
        <p v-else>Lingua Originale: {{singleSerie.original_language.toUpperCase()}}</p>
        <p>Voto: {{singleSerie.vote_average}}</p>
        <p>Overview: {{singleSerie.overview}}</p>
      </div>

    </div>
  </div>
</template>

<script>
  export default {
    name: 'CardSerie',
    props: {
      singleSerie: Object,
    },
    data(){
      return {
        flags: ["it", "en", "fr", "de", "es", "ja", "pt"],
      }
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
  .flag{
    width: 3rem;
    margin: 1rem 0;
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