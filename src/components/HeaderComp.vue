<template>
  <header
    class="p-3 d-flex justify-content-between align-items-center flex-wrap"
  >
    <div>
      <img src="../assets/netflix-logo.png" alt="logo netflix" class="logo" />
    </div>

    <div class="w-25">
      <input
        type="text"
        v-model="textInput"
        placeholder="Inserisci un titolo"
        class="py-1"
      />
      <button class="btn btn-primary ms-3" @click="$emit('search', textInput)">
        Cerca
      </button>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComp",
  data() {
    return {
      textInput: "",
    };
  },
  methods: {
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: black;
  color: red;
  .logo {
    width: 15rem;
  }
  h2 {
    margin: 1rem 0;
  }
}
</style>