<script setup>
import ProductRating from './ProductRating.vue';
const props = defineProps({
	product: Object,
});
</script>

<template>
	<div id="card">
		<!-- product image -->
		<div id="product-image">
			<img :src="product.image" alt="Product Image" />
		</div>

		<!-- product detail -->
		<div id="product-detail">
			<div id="top-detail">
				<!-- product title -->
				<h1 id="product-title">{{ product.title }}</h1>

				<!-- product type and rating -->
				<div id="type-rating">
					<p>{{ product.category }}</p>
					<ProductRating :rating="product.rating.rate" />
				</div>

				<hr />
				<!-- description -->
				<h3 id="product-description">{{ product.description }}</h3>
			</div>

			<div id="bottom-detail">
				<hr />
				<!-- product price -->
				<h1 id="product-price">${{ product.price }}</h1>
				<!-- actions button -->
				<div id="actions">
					<button id="buy-now">Buy now</button>
					<button id="next">Next product</button>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped>
div#card {
	background-color: var(--c-white);
	width: 100%;
	border-color: black;
	box-shadow: 2px 4px 21px 0 var(--color-shadow);
	border-radius: 10px;
	display: flex;
	flex-direction: row;
	padding: 50px 50px 50px 0;
}

div#card:hover {
	box-shadow: 2px 4px 100px 15px var(--color-shadow);
}

div#product-image {
	width: 40%;
	padding: 70px;
}

div#product-image > img {
	width: 100%;
	height: 100%;
}

div#product-detail {
	width: 60%;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
}

div#top-detail,
div#bottom-detail {
	display: flex;
	flex-direction: column;
	gap: 6px;
}

h1#product-title,
#product-price {
	font-weight: bold;
	color: var(--c-maroon);
}

div#type-rating {
	display: flex;
	justify-content: space-between;
	margin-top: 10px;
	padding: 0 5px 0 0;
}

h3#product-description {
	margin-top: 10px;
}

/* actions button */

div#actions {
	display: flex;
	gap: 20px;
}

div#actions button {
	width: 100%;
	border: 2px solid var(--c-maroon);
	border-radius: 4px;
	padding: 8px;
	font-size: medium;
	font-weight: 600;
	text-decoration: none;
	display: inline-block;
	cursor: pointer;
}

button:active {
	scale: 0.95;
}

button#next {
	background-color: var(--c-white);
	color: var(--c-maroon);
}

button#next:hover {
	background-color: var(--c-maroon);
	color: var(--c-white);
}

button#buy-now {
	background-color: var(--c-maroon);
	color: var(--c-white);
}

button#buy-now:hover {
	background-color: var(--c-white);
	color: var(--c-maroon);
}
</style>
