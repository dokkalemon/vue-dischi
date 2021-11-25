<template>
  <main class="full-width px-15">
      <Card 
        v-for="(album, index) in albumList"
        :key="`albumItem-${index}`"
      :img="album.poster"
      :title="album.title"
      :author="album.author"
      :years="album.year"
      :genre="album.genre"
      
      />
  </main>
</template>

<script>
import Card from '@/components/Card.vue'
import axios from 'axios';

export default {
    name: 'Main',
    components: {
        Card,
    },

    data() {
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
    }

    
}
</script>

<style scoped lang="scss">
@import '@/styles/vars';

main {
    height: 100vh;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
}




</style>