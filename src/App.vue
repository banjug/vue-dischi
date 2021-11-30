<template>
  <div id="app">
    <Header 
    @genreFilter="chosenGenre"/>
    <RecordCont/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import RecordCont from './components/RecordCont.vue'

export default {
  name: 'App',
  components: {
    RecordCont,
    Header
  },
  data() {
    return {
      chosen: ''
    }
  },
  methods: {
    chosenGenre(selezione){
      this.chosen = selezione;
      console.log(selezione);
    }
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  background-color: #1e2d3b;
  height: 100vh;
  width: 100vw;
}
</style>
