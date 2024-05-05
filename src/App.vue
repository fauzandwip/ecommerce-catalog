<script setup>
import { ref, watch } from 'vue';
import ProductCard from './components/ProductCard.vue';
import ProductLoader from './components/ProductLoader.vue';

const productId = ref(2);
const classProduct = ref('');
const product = ref(null);
const isLoading = ref(true);

const changeProductId = () => {
	if (productId.value === 20) {
		productId.value = 1;
		return;
	}
	productId.value++;
};

const fetchProductById = async (id) => {
	try {
		isLoading.value = true;
		const response = await fetch('https://fakestoreapi.com/products/' + id);
		const data = await response.json();
		const genderCategory = data.category;

		switch (genderCategory) {
			case `men's clothing`:
				classProduct.value = 'men';
				product.value = data;
				break;

			case `women's clothing`:
				classProduct.value = 'women';
				product.value = data;
				break;

			default:
				product.value = null;
				classProduct.value = 'product-unavailable';
				break;
		}

		isLoading.value = false;
	} catch (error) {
		isLoading.value = false;
		console.log(error);
	}
};

fetchProductById(productId.value);

watch(productId, async (newId) => {
	fetchProductById(newId);
});
</script>

<template>
	<div id="app" :class="classProduct">
		<main>
			<ProductLoader v-if="isLoading" />
			<ProductCard
				:product="product"
				:onClickNextButton="changeProductId"
				:classProduct="classProduct"
				v-if="!isLoading"
			/>
		</main>
	</div>
</template>

<style scoped>
div#app {
	width: auto;
	height: 70vh;
}

main {
	height: 100vh;
	display: flex;
	padding: 7%;
}

.men {
	background-color: var(--c-navy-light);
	color: var(--c-navy);
	background-image: url('@/assets/bg-pattern.svg');
}

.women {
	background-color: var(--c-pink);
	color: var(--c-maroon);
	background-image: url('@/assets/bg-pattern.svg');
}

.product-unavailable {
	background-color: var(--c-gray-light);
	background-image: none;
}
</style>
