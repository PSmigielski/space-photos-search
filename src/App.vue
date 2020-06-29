<template>
  <div id="app">
    <h1>space photos search</h1>
    <Search v-model="inputValue" @input="handleInput" />
  </div>
</template>

<script>
const debounce = require('lodash.debounce');

import axios from 'axios';

const Api = 'https://images-api.nasa.gov/search';

import Search from '@/components/Search.vue';

export default {
	name: 'App',
	components: {
		Search,
  },
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
</style>
