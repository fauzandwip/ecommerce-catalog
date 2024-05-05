<script setup>
const props = defineProps({
	rating: Number,
});

const arrRate = [1, 2, 3, 4, 5];
</script>

<template>
	<div id="rating">
		<!-- rating -->
		<p>{{ rating }}/5</p>

		<!-- circles rating -->
		<div id="circles-rate">
			<div v-for="(_, index) in arrRate" :key="index">
				<div v-if="index > rating" class="circle-rate"></div>
				<div v-if="index < rating" class="circle-rate circle-fill"></div>
			</div>
		</div>
	</div>
</template>

<style scoped>
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
	width: 16px;
	height: 16px;
	border-radius: 50%;
	border: 1px solid var(--c-maroon);
}

div.circle-fill {
	background-color: var(--c-maroon);
}
</style>
