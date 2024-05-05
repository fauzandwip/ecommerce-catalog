<script setup>
import ProductRating from './ProductRating.vue';
import ProductUnavailable from './ProductUnavailable.vue';

const props = defineProps({
	product: Object,
	onClickNextButton: Function,
	classProduct: String,
});
</script>

<template>
	<div id="card">
		<!-- unavailable product content -->
		<ProductUnavailable
			v-if="!product"
			:onClickNextButton="onClickNextButton"
		/>

		<div id="card-content" v-if="product">
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
						<ProductRating
							:rating="product.rating.rate"
							:classProduct="classProduct"
						/>
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
						<button id="buy-now" :class="classProduct">Buy now</button>
						<button id="next" @click="onClickNextButton" :class="classProduct">
							Next product
						</button>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped>
div#product-unavailable {
	background-image: url('@/assets/sad-face.svg');
}
div#card {
	background-color: var(--c-white);
	width: 100%;
	max-height: 100%;
	border-color: black;
	box-shadow: 2px 4px 21px 0 var(--color-shadow);
	border-radius: 10px;
	display: flex;
	padding: 50px 50px 50px 0;
}

div#card-content {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: center;
}

div#card:hover {
	box-shadow: 2px 4px 100px 15px var(--color-shadow);
}

div#product-image {
	width: 40%;
	padding: 70px;
	display: flex;
	justify-content: center;
	align-items: center;
}

div#product-image > img {
	width: 100%;
	max-height: 100%;
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
	line-height: 40px;
}

div#type-rating {
	display: flex;
	justify-content: space-between;
	margin-top: 10px;
	padding: 0 5px 0 0;
	color: var(--color-text);
}

h3#product-description {
	margin-top: 10px;
	color: var(--color-text);
}

/* actions button */
div#actions {
	display: flex;
	gap: 20px;
}

button {
	width: 100%;
	border-radius: 4px;
	padding: 8px;
	font-size: medium;
	font-weight: 600;
	text-decoration: none;
	display: inline-block;
	cursor: pointer;
	border-width: 2px;
}

button:active {
	scale: 0.95;
}

button#next {
	background-color: var(--c-white);
}

button#next:hover {
	background-color: var(--c-gray-light);
}

button#buy-now {
	color: var(--c-white);
}

.men {
	background-color: var(--c-navy);
	color: var(--c-navy);
	border: 2px solid var(--c-navy);
}

.women {
	background-color: var(--c-maroon);
	color: var(--c-maroon);
	border: 2px solid var(--c-maroon);
}
</style>
