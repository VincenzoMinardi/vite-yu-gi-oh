<script>
import CardHeader from './components/CardHeader.vue';
import CardList from './components/CardList.vue';
import axios from 'axios';
import { store } from './store';

export default {
	data() {
		return {
			store,
		};
	},
	components: {
    CardHeader,
    CardList,
  	},
	methods: {
		valueSelect(){
		return this.store.arrSelect.archetypes_name((option) =>{
			this.store.archetypes_name.value === option
		})
	},
},

	created() {
		// qui fare la richiesta all'api
		axios
			.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
			.then(response => (this.store.cardList = response.data.data));

			axios
			.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
			.then(response => (this.store.arrSelect) = response.data);
	},
}
</script>

<template>
	<div class="container">
		<main>
      <CardHeader />
			<CardList />
		</main>
	</div>
</template>

<style lang="scss">
* {
	
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

.html {
	
	font-family: 'Montserrat', sans-serif;
}

.container {
	background-color: rgb(212, 143, 56);
	margin: 0 auto;
	// padding: 1rem;
	// max-width: 1000px;
}

h1 {
	text-align: center;
}
</style>
