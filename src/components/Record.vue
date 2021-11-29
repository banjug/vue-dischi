<template>
    <div class="record">
        <!-- i dati dell'oggetto vengono richiamati tramite detail, prop richiamato dal componente padre  -->
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
    //   detils richiama l'oggetto del vfor del componente padre 
      details: Object,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .record {
        width: calc(20% - 40px);
        background-color: #2e3a46;
        margin: 0 20px 30px;
        padding: 20px;
        text-align: center;
        transition: all .1s ease;
        cursor: pointer;
        img {
            width: 100%;
            margin-bottom: 20px;
        }
        h3 {
            margin-bottom: 20px;
            color: white;
            font-size: 1rem;
        }
        span {
            display: block;
            color: #777d7a;
            font-size: .9rem;
        }
        &:hover {
            transform: scale(1.03);
        }

    }
</style>
