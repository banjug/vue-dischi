<template>
    <main>
        <!-- componente della selezione, importa il valore selezionato e avvia il metodo changeSelect -->
        <GenreSelection @selectedGenre="changeSelect"/>
        <section>
            <!-- vfor che stampa la lista filtrata, con details (è un prop) dice al componente figlio di prendersi i dati del singolo oggetto -->
            <Record
                v-for="record, i in filteredRecordList"
                :key="i"
                :details="record"
            />
        </section>
    </main>
</template>



<script>
import Record from '@/components/Record.vue'
import GenreSelection from '@/components/GenreSelection.vue'
import axios from "axios";
export default {
    name: 'RecordCont',
    components: {
        Record,
        GenreSelection,
    },
    data() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            recordList: [],
            selectedGenre : ''
        }
    },
    // alla creazione della pagina richiama getRecord per ottenere i dati degli elementi dall'api 
    created() {
        this.getRecord();
    },
    computed : {
        // filtra l'array degli elementi della pagina in base al valore di selectedGenre, impostato con il metodo changeSelect
        filteredRecordList(){
            if (this.selectedGenre === 'all') {
                return this.recordList
            }

            return this.recordList.filter((item) => {
                return item.genre.includes(this.selectedGenre)
            })
        }
    },
    methods: {
        // importa con axios dall'api l'array di dati di ogni elemento da stampare e li salva nell'array recordList (nei data)
        getRecord() {
            axios
            .get(this.apiUrl)
            .then((result) => {
                this.recordList = result.data.response
            })
        },
        // imposta selectedGenre(valore salvato nei data) con il valore della selezione dell'utente
        changeSelect(selezione){
            this.selectedGenre = selezione
            console.log(this.selectedGenre);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

main {
    section {
        width: 80%;
        margin: 50px auto 0;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
}

</style>
