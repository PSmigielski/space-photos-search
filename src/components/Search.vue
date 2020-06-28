<template>
    <div class="searchWrapper">
        <label for="searchBar">search</label>
        <input id="searchBar" name="search" v-model="inputValue" @input="handleInput">
    </div>
</template>

<script>
const debounce = require('lodash.debounce');

import axios from 'axios';

const Api = 'https://images-api.nasa.gov/search';

export default {
	name: 'Search',
	data() {
		return {
			inputValue: '',
			results: [],
		};
	},
	methods: {
		// eslint-disable-next-line
		handleInput: debounce(function () {
			axios.get(`${Api}?q=${this.inputValue}&media_type=image`)
				.then((response) => {
					this.results = response.data.collection.items;
					console.log(this.results);
				}).catch((e) => {
					console.log(e);
				});
		}, 500),
	},
};
</script>

<style lang="scss" scoped>
    .searchWrapper{
        border: none;
        border-bottom: 1px solid black;
    }
</style>
