<template>
   <header class="px-15">
       <div class="logo">
       <img src="@/assets/logo-spotify.png" alt="">
       </div>
       <div class="select">
           <select name="" id="">
               <option value="">All</option>
               <option value="">Rock</option>
               <option value="">Pop</option>
               <option value="">Jazz</option>
               <option value="">Metal</option>
           </select>
       </div>
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
    display: flex;

    .logo {
        border: 1px solid red;
        height: 100%;
    }
    .select {
        border: 1px solid red;
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