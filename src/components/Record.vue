<template>
    <div class="record">
        <img :src="details.poster" :alt="details.title">
        <h3>{{details.title.toUpperCase()}}</h3>
        <span>{{details.author}}</span>
        <span>{{details.year}}</span>
    </div>
</template>

<script>
export default {
  name: 'Record',
  props: {
      details: Object,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .record {
        width: calc(20% - 40px);
        background-color: #2e3a46;
        height: 300px;
        margin: 0 20px;
        text-align: center;
        img {
            width: 80%;
            margin: 15px 0;
        }
        h3 {
            margin-bottom: 15px;
            color: white;
        }
        span {
            display: block;
            color: #777d7a;
        }

    }
</style>
