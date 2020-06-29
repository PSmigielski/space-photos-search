<template>
    <input id="searchBar" name="search" :value="props" @input="handleChange" :class="{dark}">
</template>

<script>

export default {
  name: 'Search',
  props: {
    value: {
      type: String,
      required: true,
    },
    dark: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleChange(e) {
      this.$emit('input', e.target.value);
    },
  },
};
</script>

<style lang="scss" scoped>
	@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
    input{
        border: none;
		width: 300px;
		height: 30px;
		font-family: 'Poppins',sans-serif;
        border-bottom: 3px solid black;
		transition: all .3s ease-in-out;
		color:white;
		text-align: center;
		font-size: 24px;
		background: none;
		&:focus, &:visited{
			border-bottom:3px solid white;
			box-shadow: 0px 9px 16px -10px rgba(255,255,255,1);
		}
		&.dark{
			color:#313235;
			border: none;
			border-bottom:3px solid #313235;
			&:focus{
				box-shadow: 0px 9px 16px -10px #313235;
			}
		}
	}

</style>
