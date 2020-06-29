<template>
    <div :style="style" class="image"/>
</template>
<script>
export default {
  name: 'Item',
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      photoLink: this.item.links[0].href,
    };
  },
  computed: {
    style() {
      return `background: url('${this.photoLink}')`;
    },
  },
};
</script>
<style lang="scss" scoped>
    .image{
        background-position: 50% 50%;
        background-repeat: no-repeat;
        background-size: cover;
        width: 350px;
        height: 350px;
    }
    @media screen and (max-width:1560px){
      .image{
        width: 300px;
        height: 300px;
      }
    }
    @media screen and (max-width:1350px){
      .image{
        width: 250px;
        height: 250px;
      }
    }
    @media screen and (max-width: 1120px){
      .image{
        width: 350px;
        height: 350px;
      }
    }
    @media screen and (max-width: 1000px){
      .image{
        width: 300px;
        height: 300px;
      }
    }
    @media screen and (max-width: 880px){
      .image{
        width: 400px;
        height: 400px;
      }
    }
    @media screen and (max-width: 570px){
      .image{
        width: 320px;
        height: 320px;
      }
    }
    @media screen and (max-width: 450px){
      .image{
        width: 260px;
        height: 260px;
      }
    }
</style>
