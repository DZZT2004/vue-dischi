<template>
    <div class="card">
      <img :src="branoInfo.poster" alt="errore">
      <div class="titolo">{{branoInfo.title}}</div>
      <div class="artista">{{branoInfo.author}}</div>
      <div class="anno">{{branoInfo.year}}</div>
    </div>
</template>
  
<script>
export default {
  name: 'cartaCanzone',
  props: {
    branoInfo: Object,
  }
}
</script>
  
<!-- css-->
<style scoped lang="scss">
.card{
    display: flex;
    flex-direction: column;
    background-color: #2e3a46;
    padding: 10px;
    text-align: center;
    width: 200px;
    height: 300px;
    gap: 10px;
    img{
      width: 180px;
      height: 180px;
      align-self: center;
    }
    .titolo{
      color: white;
    }
    .artista, .anno{
      color: #887a6f;
    }
}
</style>
  