<template>
    <div class="background" />
</template>

<script>
export default {
  name: 'Background',
};
</script>

<style lang="scss" scoped>
    .background{
        width: 100%;
        height: 100vh;
        top:0;
        position: fixed;
        z-index:-1;
        background-image: url('../assets/background.jpg');
        background-repeat: no-repeat;
        background-size: cover;
        background-position: 50% 50%;
    }
</style>
