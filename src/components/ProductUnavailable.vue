<script setup>
const props = defineProps({
	onClickNextButton: Function,
});
</script>

<template>
	<div id="card-content">
		<div id="product-unavailable">
			<h3>This product is unavailable to show</h3>
			<button id="next" @click="onClickNextButton">Next product</button>
		</div>
	</div>
</template>

<style scoped>
div#card-content {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	color: var(--color-text);
}

div#product-unavailable {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	gap: 10px;
	width: 100%;
	height: 100%;
	background-image: url('@/assets/sad-face.svg');
	background-size: cover;
	padding-left: 50px;
	margin: 100px 50px 100px 100px;
}

button#next {
	width: 50%;
	border-radius: 4px;
	padding: 8px;
	font-size: medium;
	font-weight: 600;
	text-decoration: none;
	display: inline-block;
	cursor: pointer;
	border-width: 2px;
	background-color: white;
}

button#next:hover {
	background-color: var(--c-gray-light);
}

button:active {
	scale: 0.95;
}
</style>
