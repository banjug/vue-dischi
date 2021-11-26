<template>
  <div id="app">
    <div class="logo-cont">
      <img src="./assets/spotify.png" alt="">
    </div>
    <RecordCont/>
  </div>
</template>

<script>
import RecordCont from './components/RecordCont.vue'

export default {
  name: 'App',
  components: {
    RecordCont
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
  .logo-cont {
    height: 70px;
    padding: 10px 20px;
    background-color: #2e3a46;
    img {
      height: 100%;
    }
  }
}
</style>
