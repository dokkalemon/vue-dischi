<template>
  <main class="full-width debug">
      <Card />
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
}




</style>