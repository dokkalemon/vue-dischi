<template>
  <main class="full-width px-15">
        <div class="card-conteiner" v-if="albumArray !== null">
        
        <Card   
        v-for="(album, index) in albumArray"
        :key="`albumItem-${index}`"
        :img="album.poster"
        :title="album.title"
        :author="album.author"
        :years="album.year"
        :genre="album.genre"
        />
        </div>
        <div class="loader-conteiner" v-else>
        <Loader />
        </div>
  </main>
</template>

<script>
import Card from '@/components/Card.vue'
import Loader from '@/components/Loader.vue'
/* import axios from 'axios'; */

export default {
    name: 'Main',
    components: {
        Card,
        Loader,

    },
        props: {
            albumArray: Array,
        },

    /* data() {
        return {
            albumList: null,
        }
    },

    created() {
        this.getAlbumList()
    },

    methods: {
        getAlbumList() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => {
                this.albumList = result.data.response;
            })
            .catch(err => console.log(err))
        }
    } */

    
}
</script>

<style scoped lang="scss">
@import '@/styles/vars';

main {
    height: 100vh;
    .card-conteiner {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
    }
    .loader-conteiner {
        width: 100%;
        height: 100%;
        position: fixed;
        top: 0;
        left: 0;
        background-color: $back-color;
        display: flex;
        justify-content: center;
        align-items: center;
    }
}




</style>