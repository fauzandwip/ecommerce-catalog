<script setup>
const props = defineProps({
	rating: Number,
	classProduct: String,
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
				<div
					v-if="index > rating"
					class="circle-rate circle-not-fill"
					:class="classProduct"
				></div>
				<div
					v-if="index < rating"
					class="circle-rate"
					:class="classProduct"
				></div>
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
}

div.circle-not-fill {
	background-color: white;
}

.men {
	background-color: var(--c-navy);
	border: 1px solid var(--c-navy);
}

.women {
	background-color: var(--c-maroon);
	border: 1px solid var(--c-maroon);
}
</style>
