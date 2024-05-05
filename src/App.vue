<script setup>
import { ref } from 'vue';

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

const arr = [1, 2, 3, 4, 5];
</script>

<template>
	<div id="app">
		<main>
			<div id="card">
				<div id="product-image">
					<img :src="product.image" alt="Product Image" />
				</div>
				<div id="product-detail">
					<div id="top-detail">
						<h1 id="product-title">{{ product.title }}</h1>

						<div id="type-rating">
							<p>{{ product.category }}</p>
							<div id="rating">
								<p>{{ product.rating.rate }}/5</p>
								<div id="circles-rate">
									<div v-for="(_, index) in arr" :key="index">
										<div
											v-if="index > product.rating.rate"
											class="circle-rate"
										></div>
										<div
											v-if="index < product.rating.rate"
											class="circle-rate circle-fill"
										></div>
									</div>
								</div>
							</div>
						</div>

						<hr />
						<h3 id="product-description">{{ product.description }}</h3>
					</div>

					<div id="bottom-detail">
						<hr />
						<h1 id="product-price">${{ product.price }}</h1>
						<div id="actions">
							<button id="buy-now">Buy now</button>
							<button id="next">Next product</button>
						</div>
					</div>
				</div>
			</div>
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

div#rating {
	display: flex;
	align-items: center;
	gap: 10px;
}

div#circles-rate {
	display: flex;
	flex-direction: row;
	gap: 3px;
}

div.circle-rate {
	width: 20px;
	height: 20px;
	border-radius: 50%;
	border: 1px solid var(--c-maroon);
}

div.circle-fill {
	background-color: var(--c-maroon);
}

h3#product-description {
	margin-top: 10px;
}

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
