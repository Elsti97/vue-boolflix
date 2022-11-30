<template>
  <div>
    <h2>Lista di Serie:</h2>
    <div class="d-flex flex-wrap justify-content-center">
      <CardSerie
        v-for="(elem, index) in arraySerie2"
        :key="index"
        :singleSerie="elem"
      />
    </div>
  </div>
</template>

<script>
import CardSerie from "./CardSerie.vue";

export default {
  name: "SeriesList",
  components: {
    CardSerie,
  },
  props: {
    arraySerie2: Array,
  },
};
</script>

<style lang="scss" scoped>
h2 {
  margin: 1.5rem 1rem;
}
</style>