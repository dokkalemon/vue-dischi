<template>
  <main class="full-width debug">
      <Card 
      :img="albumList[0].poster"
      :title="albumList[0].title"
      :author="albumList[0].author"
      :years="albumList[0].year"
      :genre="albumList[0].genre"
      
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
    height: calc(100vh - 60px);
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
}




</style>