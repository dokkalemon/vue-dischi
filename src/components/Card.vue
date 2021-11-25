<template>
  <section  class="card">
        <div class="card-conteiner">
            <div class="img">
                <img :src="img" alt="">
            </div>
        <div class="info">
            <h2>{{ title }}</h2>
            <h3>{{ author }}</h3>
            <h4>{{ years }}</h4>
            <h5>{{ genre }}</h5>

        </div>
      </div>
  </section>
</template>

<script>
export default {
    name: 'Card',

    props: {
        img: String,
        title: String,
        author: String,
        years: String,
        genre: String
    }
}
</script>

<style scoped lang="scss">
@import '@/styles/vars';

.card {
    width: calc(100% / 8);
    padding: 10px 20px;
    height: 420px;
    .card-conteiner {
        background-color: $primary-color;
        height: 100%;
        .img{
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 200px;
            img {
                object-fit: contain;
            width: 100%;
            
            }
        }
        .info {
            text-align: center;
            h2 {
                text-transform: uppercase;
                padding: 15px;
                font-size: 20px;
            }
            h3 {
                color: $secondary-color;
                padding: 0 0 10px 0;
            }
            h4 {
                color: $secondary-color;
                padding: 0 0 10px 0;
            }
            h5 {
                padding: 0 0 30px 0;
            }
     
        }
    }
}

</style>