<template>
    <main>
        <Record/>
    </main>
</template>

<script>
import Record from '@/components/Record.vue'
export default {
    name: 'RecordCont',
    components: {
        Record
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
