<template>
  <div>
    <div class="card">
      <img :src="`http://image.tmdb.org/t/p/w342/${singleFilm.poster_path}`" alt="">
      <div class="titles">
        <p>Titolo: {{singleFilm.title}}</p>
        <p>Titolo Originale: {{singleFilm.original_title}}</p>
        <img v-if="flags.includes(singleFilm.original_language)" :src="require(`../assets/${singleFilm.original_language}.svg`)" class="flag">
        <p v-else>Lingua Originale: {{singleFilm.original_language.toUpperCase()}}</p>
        <p>Voto: {{singleFilm.vote_average}}</p>
        <p>Overview: {{singleFilm.overview}}</p>
        </div>
  
    </div>
  </div>
</template>

<script>
  export default {
    name: 'CardFilm',
    props: {
      singleFilm: Object,
    },
    data(){
      return {
        flags: ["it", "en", "fr", "de", "es", "ja", "pt"],
      }
    },
    methods: {
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