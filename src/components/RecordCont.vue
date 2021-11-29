<template>
    <main>
        <GenreSelection/>
        <section>
            <Record @selectedGenre="changeSelect"
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
        }
    },
    created() {
        this.getRecord();
    },
    computed : {
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
        getRecord() {
            axios
            .get(this.apiUrl)
            .then((result) => {
                this.recordList = result.data.response
            })
        },
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
