<template>
  <div>
    <div class="card">
      {{starsRating()}}
      <img v-if="singleFilm.poster_path" :src="`http://image.tmdb.org/t/p/w342/${singleFilm.poster_path}`" alt="copertina film">
      <img v-else src="../assets/img-not-found.png" class="not-img">
      <div class="titles">
        <p>Titolo: {{ singleFilm.title }}</p>
        <p>Titolo Originale: {{ singleFilm.original_title }}</p>
        <img
          v-if="flags.includes(singleFilm.original_language)"
          :src="require(`../assets/${singleFilm.original_language}.svg`)"
          class="flag"
        />
        <p v-else>
          Lingua Originale: {{ singleFilm.original_language.toUpperCase() }}
        </p>
          <div class="d-flex">
            <p class="me-2">Voto: {{ singleFilm.vote_average }}/10</p>
            
            <div v-for="x in stellaPiena" :key="x">
              <font-awesome-icon icon="fa-solid fa-star" class="gold" />
            </div>
            <div v-if="mezzaStella == true">
              <font-awesome-icon
                icon="fa-solid fa-star-half-stroke"
                class="gold"
              />
            </div>
            <div v-for="x in stellaVuota" :key="'k' + x">
              <font-awesome-icon icon="fa-regular fa-star" class="gold" />
            </div>
          </div>

        <p>Overview: {{ singleFilm.overview }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardFilm",
  props: {
    singleFilm: Object,
  },
  data() {
    return {
      flags: ["it", "en", "fr", "de", "es", "ja", "pt"],
      mezzoVoto: "0",
      stellaPiena: "0",
      stellaVuota: "0",
      mezzaStella: false,
    };
  },
  methods: {
    starsRating() {
      this.mezzoVoto = this.singleFilm.vote_average / "2";

      if (this.mezzoVoto != Math.floor(this.mezzoVoto)) {
        this.mezzaStella = true;
        this.stellaPiena = Math.floor(this.mezzoVoto);
        this.stellaVuota = "5" - this.stellaPiena - "1";
      } else {
        this.mezzaStella = false;
        this.stellaPiena = this.mezzoVoto;
        this.stellaVuota = "5" - this.stellaPiena;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  position: relative;
  .not-img{
    width: 342px;
    height: 500px;
  }
}
.titles {
  display: none;
  h4 {
    display: inline;
  }
  .flag {
    width: 3rem;
    margin: 1rem 0;
  }
}
.card:hover .titles {
  padding: 2rem 1rem 0;
  width: 100%;
  height: 100%;
  background-color: black;
  color: white;
  opacity: 0.9;
  position: absolute;
  display: inline;
  overflow: auto;
  cursor: pointer;
}

.gold {
  color: gold;
}
</style>