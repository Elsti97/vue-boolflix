<template>
  <div>
    <h2>Lista di Film:</h2>
    <div class="d-flex flex-wrap justify-content-center">
      <CardFilm
        v-for="(elem, index) in arrayFilm2"
        :key="index"
        :singleFilm="elem"
      />
    </div>
  </div>
</template>

<script>
import CardFilm from "./CardFilm.vue";

export default {
  name: "FilmsList",
  components: {
    CardFilm,
  },
  props: {
    arrayFilm2: Array,
  },
};
</script>

<style lang="scss" scoped>
h2 {
  margin: 1.5rem 0;
}
</style>