<template>
	<div class="appWrapper" :class="state ? 'start' : '' ">
    <Content v-if="state===0"/>
		<Search v-model="inputValue" @input="handleInput" :dark="state ===1"/>
    <transition name="opacityChg">
      <Background v-if="state===0"/>
    </transition>
    <div class="results" v-if="results && !load && state ===1">
      <Item v-for="item in results" :key="item.data[0].nasa_id" :item="item" />
    </div>
	</div>
</template>

<script>
import Content from '@/components/Content.vue';

import Search from '@/components/Search.vue';

import Background from '@/components/Hero.vue';

import Item from '@/components/Item.vue';

import axios from 'axios';

const debounce = require('lodash.debounce');

const Api = 'https://images-api.nasa.gov/search';

export default {
  name: 'App',
  components: {
    Search,
    Background,
    Content,
    Item,
  },
  data() {
    return {
      load: false,
      state: 0,
      inputValue: '',
      results: [],
    };
  },
  methods: {
    // eslint-disable-next-line
		handleInput: debounce(function () {
      this.load = true;
      axios.get(`${Api}?q=${this.inputValue}&media_type=image`)
        .then((response) => {
          this.results = response.data.collection.items;
          this.load = false;
          this.state = 1;
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
  .opacityChg-enter-active, .opacityChg-leave-active{
    transition: opacity .5s ease;
  }
  .opacityChg-enter, .opacityChg-leave-to{
    opacity:0;
  }
  .appWrapper{
		width: 100vw;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
    flex-direction: column;
    &.start{
      justify-content: flex-start;
      margin-top:40px;
    }
	}
  .results{
    width: 70%;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap:20px;
    align-items: center;
    justify-items: center;
    margin-top:20px
  }
</style>
