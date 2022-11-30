<template>
    <div class="corpo">
      <div id="head">
        {{inizializza()}}
        <FontAwesomeIcon icon="fa-brands fa-spotify" class="icona"/>
        <genreOption
        :genres-list="genresList"
        @changedGenre="genreChange"/>
      </div>
      <div id="canzoni">
        <cartaCanzone
          v-for="brano in arrayFiltrati"
          :branoInfo="brano"
          :key="brano.title"
        />
      </div>
    </div>
</template>
  
<script>
import cartaCanzone from '@/components/Card.vue'
import genreOption from '@/components/Genre.vue'

export default {
  name: 'corpoPage',
  components: {
    cartaCanzone,
    genreOption
  },
  props: {
    arrMusic: Array,
  },
  data() {
    return {
      genresList: [],
      arrayFiltrati: [],
      genreFilter: 'all',
    }
  },
  methods: {
    genreChange(filtro) {
      console.log(filtro)
      this.arrayFiltrati = [];
      this.genreFilter = filtro;
      if(filtro != "all"){
        this.arrMusic.forEach((item) =>{
        if(item.genre == filtro){
          this.arrayFiltrati.push(item);
        }
      })
      }else{
        this.arrayFiltrati = this.arrMusic;
      }
    },
    inizializza(){
      if(this.genreFilter == "all"){
        this.arrayFiltrati = this.arrMusic;
      }
    }
  }
}
</script>
  
<!-- css-->
<style scoped lang="scss">
#head{
  background-color: #2e3a46;
  height: 70px;
  .icona{
    float: left;
    color: green;
    font-size: 46px;
    margin: 12px;
  }
}

#canzoni {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  background-color: #1e2d3b;
  padding: 50px 340px 50px 340px;
  gap: 30px;
  min-height: 759px;
  height: 100%;
}
</style>
  