<script>
export default {
  name: "CardApp",
	props: {
		card: Object,
	},
};
</script>

<template>
	<div class="card">
		<img :src="card.card_images[0].image_url" :alt="card.name"/>
		<h2 class="type">{{ card.name }}</h2>
		<div class="species">{{ card.def }}</div>
	</div>
</template>


<style lang="scss" scoped>
.card {
	
	padding: 2rem 1rem;
	border: 2px solid brown;
	text-align: center;
	img {
	// border-radius: 9em;
	max-width: 100%;
	
}
}


</style>
