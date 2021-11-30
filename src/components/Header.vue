<template>
    <header>
        <img src="../assets/spotify.png" alt="">

        <div class="select">
            Seleziona un genere musicale:
            <!-- $emit manda il valore della selezione al componente padre per generare solo gli elementi selezionati -->
            <select name="genre" id="genre" 
            v-model="selectedGenre" 
            @change="$emit('genreFilter', selectedGenre)">
                <option selected value="all">Tutti</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </div>

        <!-- <GenreSelection 
        @selectedGenre="changeSelect" 
        @changeSelect="$emit('genreFilter', selectedGenre)" /> -->
    </header>
</template>

<script>
// import GenreSelection from '@/components/GenreSelection.vue'

export default {
    name: 'Header',
    components: {
        // GenreSelection,
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
    .select {
    margin: 30px 0;
    text-align: center;
    color: white;
    #genre {
      margin: 0 10px;
    }
  }
  }
</style>