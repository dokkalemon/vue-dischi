<template>
   <header class="px-15">
       <img src="@/assets/logo-spotify.png" alt="">
   </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped lang="scss">
@import '@/styles/vars';

header {
    height: 60px;
    padding: 5px;
    background-color: $primary-color;
}



</style>