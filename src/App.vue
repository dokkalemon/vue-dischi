<template>
  <div class="app">
    <!-- Header -->
    <Header @changeGenre="setGenre"/>

    <!-- Main -->
    <Main :albumArray="filteredAlbum"/>

  </div>

</template>

<script>
import axios from 'axios'
import Header from '@/components/Header.vue'
import Main from '@/components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },

  data() {
        return {
            albumList: null,
            selectedGenre: '',
        }
    },

    computed: {
        filteredAlbum() {
           if (this.selectedGenre === '') {
             return this.albumList;
           }
           return this.albumList.filter(item => {
             return item.genre.toLowerCase().includes(this.selectedGenre.toLowerCase())
           })
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
        },

        setGenre(prova) {
          this.selectedGenre = prova
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/vars.scss';
@import '@/styles/global.scss';

</style>
