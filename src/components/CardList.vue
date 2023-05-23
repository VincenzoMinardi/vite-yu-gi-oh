<script>
import CardApp from './CardApp.vue';
import { store } from '../store';

export default {
	data() {
		return {
			store,
		};
	},
	components: {
		CardApp,
	},
};
</script>

<template>
	<div class="bar-black">
		<h2>Found 20 Cards</h2>
	</div>

    <select v-model="store.arrSelect" class="button-card" placeholder="Seleziona">
        <option v-for="option in store.arrSelect" class="option-card">{{option.archetype_name}}</option>
    </select>
	<button class="bt">Search</button>
	<button class="bt">Reset</button>
	<div class="color">
		<div class="cards-container">
			<CardApp
				v-for="(card, index) in store.cardList"
				:key="index"
				class="card-character"
				:card="card"
		/>
		</div>
	</div>
	
</template>

<style lang="scss" scoped>

.bar-black{
	background-color: black;
	height: 60px;
	h2{
		color: white;
	}
}

.cards-container {
	
	display: flex;
	flex-wrap: wrap;
	.card-character {
	flex: 0 0 25%;
}
	
}

.button-card{
	height: 40px;
	width: 150px;
margin: 3rem;
}

.bt{
	height: 30px;
	width: 150px;
	margin-left: 1rem;
}


</style>
