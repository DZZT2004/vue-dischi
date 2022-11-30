<template>
    <div id="genre">
      <label for="select-genres">
        Genere
      <select
        id="select-genres"
        v-model="genreFiltro"
        name="genre"
        @change="cambiaGenere"
      >
        <option value="all">
          all
        </option>
        <option
          v-for="genre in genreLista"
          :key="genre"
          :value="genre"
        >
          {{ genre }}
        </option>
      </select>
    </label>
    </div>
</template>
  
<script>
  
export default {
  name: 'genreOption',
  props: {
    genreArray: Array
  },
  data() {
    return {
      genreFiltro: "all",
      genreLista: ["Pop", "Rock", "Jazz", "Metal"]
    }
  },
  methods: {
    cambiaGenere() {
      this.$emit('changedGenre', this.genreFiltro)
    },
  }
}
</script>
  
<!-- css-->
<style lang="scss">
#genre {
  label{
    color: white;
  }
  label, select{
    margin-top: 20px;
    margin-right: 50px;
  }
}
</style>
  