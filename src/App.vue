<template>
  <div id="app">
    <corpoPage
      :arrMusic="brani"
    />
  </div>
</template>

<script>
import axios from 'axios'
import corpoPage from './components/Corpo.vue'

export default {
  name: 'App',
  components: {
    corpoPage
  },
  data() {
    return {
      brani: null
    }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((axiosResponse) => {
        this.brani = axiosResponse.data.response;
        console.log(this.brani)
      });
  }
}
</script>

  <!-- css-->
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  height: 100%;
}
</style>
