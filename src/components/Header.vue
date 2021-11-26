<template>
   <header class="px-15">
       <div class="logo">
       <img src="@/assets/logo-spotify.png" alt="">
       </div>
       <div class="select">
           <select name="genreAlbum" id="" v-model="genreInput" @change="$emit('changeGenre', genreInput)">
               <option value="all">All</option>
               <option value="rock">Rock</option>
               <option value="pop">Pop</option>
               <option value="jazz">Jazz</option>
               <option value="metal">Metal</option>
           </select>
       </div>
   </header>
</template>

<script>
export default {
    name: 'Header',

    data() {
        return {
            genreInput: '',
        }
    }
}
</script>

<style scoped lang="scss">
@import '@/styles/vars';

header {
    height: 60px;
    padding: 5px;
    background-color: $primary-color;
    display: flex;

    .logo {

        height: 100%;
    }
    .select {

        flex-grow: 1;
        display: flex;
        justify-content: flex-end;
        padding: 10px;
        select {
            background-color: transparent;
            border: none;
            border-bottom: 1px solid white;
            width: 200px;
            font-size: 20px;
        }
        option {
            background-color: $primary-color;
            color: white;
        }
    }
}



</style>