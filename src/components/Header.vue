<template>
    <header>
      <img src="../assets/spotify.png" alt="">
        <GenreSelection 
        @selectedGenre="changeSelect" 
        @changeSelect="$emit('genreFilter', selectedGenre)" />
    </header>
</template>

<script>
import GenreSelection from '@/components/GenreSelection.vue'

export default {
    name: 'Header',
    components: {
        GenreSelection,
    },
    data() {
        return {
            selectedGenre : ''
        }
    },
    methods: {
        // imposta selectedGenre(valore salvato nei data) con il valore della selezione dell'utente
        changeSelect(selezione){
            this.selectedGenre = selezione
            console.log(this.selectedGenre);
        }
    }
    
}
</script>

<style lang="scss" scoped>
header {
    height: 70px;
    padding: 10px 20px;
    background-color: #2e3a46;
    display: flex;
    justify-content: space-between;
    align-items: center;
    img {
      height: 100%;
    }
  }
</style>