<template>
    <main>
        <Record
            v-for="record, i in recordList"
            :key="i"
            :details="record"
        />
    </main>
</template>

<script>
import Record from '@/components/Record.vue'
import axios from "axios";
export default {
    name: 'RecordCont',
    components: {
        Record
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
    methods: {
        getRecord() {
            axios
            .get(this.apiUrl)
            .then((result) => {
                this.recordList = result.data.response
                // console.log(result.data.response);
            })
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

main {
    width: 80%;
    margin: 50px auto 0;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}

</style>
