<template>
    <div class="record">
        <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
        <h3>NEW JERSEY</h3>
        <span>Bon Jovi</span>
        <span>1988</span>
    </div>
</template>

<script>
export default {
  name: 'Record',
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
