<template>
    <div class="searchWrapper">
        <label for="searchBar">search</label>
        <input id="searchBar" name="search" :value="props" @input="handleChange">
    </div>
</template>

<script>


export default {
	name: 'Search',
	props: {
		value:{
			type:String,
			required:true,
		}
	},
	methods:{
		handleChange(e){
			this.$emit('input', e.target.value);
		}
	}
};
</script>

<style lang="scss" scoped>
    .searchWrapper{
        border: none;
        border-bottom: 1px solid black;
    }
</style>
