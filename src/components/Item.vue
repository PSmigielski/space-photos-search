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
</style>
