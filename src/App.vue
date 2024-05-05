<script setup>
import { ref } from 'vue';
import ProductCard from './components/ProductCard.vue';

const product = ref({
	id: 1,
	title: 'Fjallraven - Foldsack No. 1 Backpack, Fits 15 Laptops',
	price: 109.95,
	description:
		'Your perfect pack for everyday use and walks in the forest. Stash your laptop (up to 15 inches) in the padded sleeve, your everyday',
	category: "men's clothing",
	image: 'https://fakestoreapi.com/img/81fPKd-2AYL._AC_SL1500_.jpg',
	rating: {
		rate: 3.9,
		count: 120,
	},
});
</script>

<template>
	<div id="app">
		<main>
			<ProductCard :product="product" />
		</main>
	</div>
</template>

<style scoped>
div#app {
	width: auto;
	height: 70vh;
	background-color: var(--c-pink);
	background-image: url('@/assets/bg-pattern.svg');
}

main {
	height: 100vh;
	display: flex;
	padding: 10%;
}
</style>
