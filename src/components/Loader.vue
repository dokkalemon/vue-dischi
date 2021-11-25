<template>
  <div class="loader">
      <h2>Please Wait!</h2>
      <img src="@/assets/spotify.svg" alt="">
      <h4>Loading...</h4>
  </div>
</template>

<script>
export default {
    name: 'Loader'
}
</script>

<style scoped lang="scss">
@import '@/styles/vars';

.loader {
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: $primary-color;
    box-shadow: 0px 10px 15px rgba(0, 0, 0, 0.194);
    img {
        padding: 20px;
        height: 100px;
        animation: spin 0.5s infinite alternate

    }

    @keyframes spin {
        from {transform: scale(1)}
        to {transform: scale(1.3)}
    }
}

</style>