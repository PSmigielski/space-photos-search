<template>
	<div class="appWrapper">
    <Content />
		<Search v-model="inputValue" @input="handleInput" />
		<Background />
	</div>
</template>

<script>
import Content from '@/components/Content.vue';

import Search from '@/components/Search.vue';

import Background from '@/components/Hero.vue';

import axios from 'axios';

const debounce = require('lodash.debounce');

const Api = 'https://images-api.nasa.gov/search';

export default {
  name: 'App',
  components: {
    Search,
    Background,
    Content,
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
	@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
  *{
    margin:0px;
    padding: 0px;
    box-sizing: border-box;
  }
  .appWrapper{
		width: 100vw;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
    flex-direction: column;
	}
</style>
